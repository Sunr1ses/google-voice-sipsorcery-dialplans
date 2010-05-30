How many times you misdialed a number and ended up calling to some exotic 
country or a satellite network which had a bad impact on your bill? If none, 
this topic is probably not for you.

Complex dialplan is equipped with two safeguards (disabled by default) to 
prevent you from inadvertent calling to undesired destination.

First is an array of blessed country codes:

Allowed_Country = %w{  
1 33 36 39 41 420 44 49 7 86 883 886 90 972
}

If the number you dialed (in ENUM, 'international' format) does not begin 
with one of these codes, your call will fail with code 503 and "Calls to 
this country not allowed" error message. To advanced users: each element 
of the array is treated as a regular expression pattern. For example, 
37[1-3] will correspond to 371, 372 and 373 country codes.

Second is an array of excluded country / area codes:

ExcludedPrefixes = [
   ' 1 (900 | 809)',               # USA Premium
   ' 1 \d\d\d 555 1212',           # USA Directory assistance
   '44 (9 | 55 | 70 | 84 | 87)',   # UK Premium
   '49 (1 [^567] | 900)',          # Germany Premium
   '39 (1 | 84 | 89)',             # Italy Premium 
   '420 90',                       # Czech Premium 
]

Each element is a regular expression (or a simple string) defining phone 
number prefix you'd like to exclude. For example, the first element excludes 
1900 and 1809 numbers. Spaces are ignored, so feel free to use them to make 
the patterns more readable.

If dialed number matches one of the ExcludedPrefixes patterns, the call will 
fail with 503 code and 'Calls to ...* not allowed' message.

What if you need to call one of prohibited numbers and you don't have 
computer handy to edit your dialplan? Well, you can use #n prefix to force 
VoIP provider. In this case, the dialplan will bypass safeguard checks and 
your call will be routed to provider n.

Finally, don't forget to uncomment EnableSafeguards:

# Uncomment line below to enable misdialing safeguards

EnableSafeguards = 1