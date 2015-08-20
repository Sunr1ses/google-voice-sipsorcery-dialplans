# Introduction #

The dialplan supports several Google Voice accounts, so you can use different
GV numbers depending on callee's area code (or you can use one GV number to
check voicemail on the other).

Each Google Voice account can have several callback numbers linked to it.
When you place a call, the dialplan will alternate callbacks in random or
sequential order.

For incoming calls, the dialplan will look for caller's name in CNAM hash
table. If caller's number is not in the table and country code is 1 (USA),
the dialplan will (optionally) use White Pages' reverse lookup to determine
caller's name or, if the number's unpublished, the city and state it originates
from.

# Details #


Configuration:

First, you need to describe your Google Voice account(s). It can be best
explained by example:

1. Suppose you have just one GV account and one callback number on it. Then the following description will do:

```
GVaccount = [
{ :usr => 'login', :pwd => 'pass', :cb => '(206) 242-1234' }
]
```

Or, you can break it into 3 lines:

```
GVaccount = [{
  :usr => 'login',         # Your GV login name, with our without @gmail.com
  :pwd => 'pass',          # Your GV password
  :cb  => '(206) 242-1234' # Callback number in 10- or 11-digit notation.
                           # Add fancy chars to your taste, they are ignored :-)
}]
```

2. What if you have two or more callback numbers? Then every element of GVaccount array should contain :usr and :pwd and therefore, it's logical to separate common part from variable. So, we declare common part as "Credentials":

```
Credentials = { :usr => 'login', :pwd => 'pass' } # Your GV login and password
```

and then use it in each element, adding variable parameters like callback number:

```
GVaccount = [
  Credentials + { :cb => '(206) 242-1234' }, # IPKall callback number
  Credentials + { :cb => '(747) 234-5678' }, # Gizmo callback number
]
```

3. What if we have several GV accounts? Then we declare them using #1 or #2 approach above, depending on the number of callbacks to each account:

```
PAaccount = [{
  :usr => 'PAlogin',       # Your GV login name, with our without @gmail.com
  :pwd => 'PApass',        # Your GV password
  :cb => '(206) 242-1234'  # Callback number in 10- or 11-digit notation. 
                           # Add fancy chars to your taste :-)
}]

NYuser = { :usr => 'NYlogin', :pwd => 'NYpas' } # Your GV login and password

NYaccount = [
  NYuser + { :cb => '(206) 242-1234' }, # IPKall callback number
  NYuser + { :cb => '(747) 234-5678' }, # Gizmo callback number
]
```

Now, what you do with several GV accounts? Apparently you select appropriate account, depending on area code of your callee. What is the logical place to do it? Right, in the selectVSP method!

You'll find a method call in there:

```
gvcall GVaccount
```

It's called for all area codes except 747 (Gizmo). So, you need to modify
case...when statement as follows:

```
when "747"                   
route(6,"Gizmo5 to Gizmo5 call")
when "212", "718", "516", "347", "917", "646" # NY, I have GV number there
gvcall NYaccount         
else
gvcall PAaccount
```

If you want to use your "other" GV account for checking voicemail your primary GV, put the following right after case @num:

```
case @num
when "12125551212"                   # My Google Voice number
gvcall VMaccount                     # call it using my other GV account
```

gvcall method accepts two more arguments (optional): number or retries and initial index. If you want it to make 2 attempts using callback numbers linked to NYaccount in sequential order, put

```
gvcall NYaccount, 2
```

If you want it do the same in random order, then use this line:

```
gvcall NYaccount, 2, @t.to_i
```

Second, you need to populate CNAM hash table with phone numbers and names of your callers. Note that the numbers must be in ENUM format (country code followed by area code and then phone number). No spaces, no fancy chars here!

And finally, you can obtain White Pages API key at:

http://developer.whitepages.com/

and insert it where indicated (right below CNAM hash table). Don't forget to
remove the pound sign in the beginning of WP\_key line to uncomment it.