# Please Note #

All the steps described here were stolen shamelessly from YouTube user toddjihad's excellent [video](http://youtu.be/jS50Fld3y8w) posted last August, called "Free WIFI / VOIP calls using your Android device by a free hosted SIP server." I take credit for none of this, and am only posting here after having followed the steps and successfully placed a call.

Todd's steps are specific to Android devices running a custom ROM, but based on the success I had, it should work with any SIP client. You're effectively using an Android device to establish the correct parameters in pbxes, but any SIP client should do once you're all setup.

# Todd's High Level Steps #

  1. Install the Google Voice app on your phone
  1. Ensure that Google Chat is activated as a managed phone on you Google Voice settings page
  1. Download and install sipdroid
  1. Start sipdroid and at the bottom, click "New PBX linked to my Google Voice"; take down the SIP userid sipdroid created for you. It should be your Google userid with "-200" appended
  1. Uninstall sipdroid
  1. Log into pbxes with your Google username (username only, do not append "-200")
  1. Go to the Personal Data page and complete your address and main phone number details. They will delete your account if you don't do this.
  1. Under extensions, click on "sipdroid 200" and enter your Google Voice password in the password field and your outbound caller ID if you wish
  1. Click Submit at the bottom and then the red bar text to Apply the changes at the top
  1. Now return to your phone, go into Settings -> Call Settings
  1. Scroll to the bottom and click Accounts
  1. Turn on Receive Incoming calls and then click Add Account
  1. Enter your SIP id in the Username field (your Google Voice username with "-200" appended) and your password in the password field.
  1. Go into Optional Settings and change the transport to TCP
  1. Back out, and you should see the new account listed. It may take a couple of login attempts, but if you entered everything correctly you should see "Primary account. Receiving calls." written underneath the new account username.

That should be it.

# My personal experience #

I am currently using an unsubscribed HTC Nexus One as a pure wifi phone, so my experience may differ slightly from others who have a SIM card inserted and have a voice and/or data plan as well. When I followed Todd's steps, I was unable to dial out. First I tried to call with Airplane Mode turned on (but with wifi turned on) and the phone asked me to come out of Airplane Mode. With Airplane Mode off, I was still unable to call as the phone complained about the data network not being available. So here's how I tweaked Todd's instructions and got outbound dialing working:

  1. Install the Google Voice app on your phone
  1. Ensure that Google Chat is activated as a managed phone on you Google Voice settings page
  1. Download and install sipdroid
  1. Start sipdroid and at the bottom, click "New PBX linked to my Google Voice"; take down the SIP userid sipdroid created for you. It should be your Google userid with "-200" appended
  1. Log into pbxes with your Google username (username only, do not append "-200")
  1. Go to the Personal Data page and complete your address and main phone number details. They will delete your account if you don't.
  1. Under extensions, click on "sipdroid 200" and enter your Google Voice password in the password field and your outbound caller ID if you wish
  1. Click Submit at the bottom and then the red bar text to Apply the changes at the top
  1. Sipdroid Line 1 should already be configured with the credentials that sipdroid created for you on pbxes.org. Make sure you have a green dot in the notification area, indicating successful logon to pbxes.
  1. When I place a call using the dialer, the device realizes that the only eligible dialout mechanism is siproid, and places the call via sipdroid automatically.

That's it. Install sipdroid, tell it to create an account for you at pbxes. Log into pbxes to complete the Personal Data page and enter your Google Voice password on your "sipdroid 200" extension page. Start placing calls via sipdroid.

# Learn more about sipdroid #
If you would like to learn more about sipdroid or if you need to contact the developers, please visit their site, also hosted here at Google Code

http://code.google.com/p/sipdroid/

# Note #

I have been experiencing SIP Sorcery's "rnr se key" error since last year and have been dialing via the Google Voice mobile web page ever since. The mechanism that pbxes uses is not the same as SIP Sorcery because my outbound dialing has been restored.

Many thanks again to toddjihad on YouTube. His tutorial was straightforward and very easy to follow.

Enjoy!