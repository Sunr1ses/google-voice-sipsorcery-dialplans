# Background #

IPComms.net is a company offering business-class telephony services. This includes providing inbound PSTN-to-SIP gateway services. This wiki page describes how to forward incoming calls to SIP Sorcery via SIP, similar to the way that we use IPKall.

# Configuration #

Sign up for an IPComms account and after it’s all good to go, register the account with your sipsorcery account just like you would sipgate using the info you get from ipcomms
Use the ipcomms number where you would have used the sipgate number

You need to set up DID routing in your IPComms account too so log in and then log into your account

Then click on "View DID Routing":

![http://farm6.static.flickr.com/5259/5523508182_55199b102b_b.jpg](http://farm6.static.flickr.com/5259/5523508182_55199b102b_b.jpg)

You may be asked to authenticate again. Login if asked. Then click "DID" on the left:

![http://farm6.static.flickr.com/5012/5523508222_f48ba4b9cd_b.jpg](http://farm6.static.flickr.com/5012/5523508222_f48ba4b9cd_b.jpg)


You will see the page where you make the changes. Follow these steps to configure the forwarding.

  1. Click “Manage DID Routing” in the center of the page
  1. Select your virtual phone number from the list
  1. Select “VOIP Call : Yes"
  1. Enter your SIP Sorcery credentials in this format: "sip/username@sipsorcery.com"
  1. click “Add phone number" and it should appear below

Manage DID Routing -

![http://farm6.static.flickr.com/5132/5522916643_28f6274dae_b.jpg](http://farm6.static.flickr.com/5132/5522916643_28f6274dae_b.jpg)

That's it! Calls arriving inbound to your IPComms PSTN number should now forward to your SIP Sorcery account, just as they do from IPKall.

Many thanks to Red Leatherman for providing the screenshots and content.