This dialplan is a variation of Simple Dial Plan supporting calling your
GV voice mail from ATA and CNAM.

Google Voice doesn't allow you to call your own GV number. It means that
you can't check voice mail unless you use some other Google Voice account
to call your "main" GV number. This dialplan does just that.

So, if you have 2nd GV account, you need to uncomment and edit 3 lines:

GV_NUMBER = '12125551212'          # My GV number
VM_USER   = 'username@gmail.com'   # my 2nd GV e-mail address (user@gmail.com)
VM_PASS   = 'GV password'          # my GV password 

First line is your "main" GV number in 11-digit format. The other two lines
are your credentials for 2nd GV account. If you dial GV_NUMBER, the dialplan
will use these credentials.

Note that both GV accounts should share callback numbers (Settings / Phones).

You can use speed dial to program VM number (GV_NUMBER) to, say, 1 and dial 1
instead of the number.

CNAM hash table and WP_key are documented in readme for "Complex Dial Plan 
with CNAM lookup".

This dialplan can use more than one callback number, just use an array instead
of simple string:

CB_NUMBER = [ '12125551212', '12124441212' ]

Likewise, you can use array of time-outs, should you need to set different
time-outs for different numbers:

TIME_OUT  = [ 10, 15 ]

Dialplan will try callback numbers sequentially, starting from the first in
your array.