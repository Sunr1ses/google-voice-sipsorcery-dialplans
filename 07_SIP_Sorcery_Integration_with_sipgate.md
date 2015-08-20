# Sipgate (Temporarily) Unavailable #
Unfortunately, sipgate's signup page now features a notice that they are no long able to provide this service to new users. I will retain the original content below for users who already have accounts, and also just in case the service gets restored.

Almost all service providers discussed on this site have temporarily halted their service at time or another, so there's a chance that sipgate may return.

In the meantime, please return to the wiki [table of contents](http://code.google.com/p/google-voice-sipsorcery-dialplans/w/list) and read wiki pages 6, 8, 9 and 10 to learn what other options are still available today.

# Original Content #
**Note:** In order to use SIP Sorcery as intended in this context, be advised that you must enter your Google Voice userid and password **unencrypted** on a publicly-accessible system. SIP Sorcery takes care to ensure the privacy and security of your private information, but it is up to you to consider the risks involved in storing those details on a system not controlled by you and the implications of your Google account details potentially being exposed should the server be compromised.

SIP Sorcery is not only able to process and route SIP calls, but is also able to serve as a SIP client to SIP providers. This capability enables SIP Sorcery users to use any other telecom provider that offers SIP access to their users' phone lines. Sipgate.com is one such provider. In order to enable 24x7 free calling for Google Voice and sipgate users using just a SIP client, follow these simple steps to select and use a dialplan available in the Source section of this site.

  1. Sign up for a free Residential Sipgate ONE account at sipgate.com. Go into your settings page and take note of both your regular phone number (usually in area code 415) as well as your SIP credentials.
  1. Sign up for a free account at SIPSorcery.com.
  1. On the SIP Providers page, add a new provider named "sipgate" and enter your SIP username and password provided by sipgate. Enter sipgate.com as the server. Check the "Register" checkbox and make sure that the registered contact shows "sip:" followed your SIP Sorcery name and "@sipsorcery.com". Click Add when you have finished. After a few seconds, sipgate should automatically appear in the "SIP Provider Registrations" list at the bottom of the screen. If it does not, double check the SIP credentials and server settings against those shown on your sipgate account settings page.
  1. Configure your SIP client, SIP-compatible softphone or SIP-compatible ATA to login to your sipsorcery account. Check the "SIP Accounts" page of your SIP Sorcery account and make sure an entry appears in the "SIP Bindings" list at the bottom of the page.
  1. Use a phone to call your sipgate number and make sure the phone attached to your SIP Sorcery account rings. Answer the call and make sure you can hear sound in both directions.
  1. Login to Google Voice, click Settings, Phones, and add your sipgate phone number as a new managed phone. Google Voice will display a two digit number on your screen. Click Connect and Google Voice will call your sipgate number and ask you to enter the code displayed. Once you successfully add the new line, make sure it is checked on your Google Voice phone list.

Note: You are now ready to receive inbound calls to your Google Voice number for free. You may also enter phone numbers on the Google Voice website and select your sipgate number as the phone you wish to use to make free outbound calls. There is one last step required to enable 24x7 free unlimited outbound dialing from your SIP-compatible softphone or standard telephone attached to your SIP-compatible ATA.<p>

As the final step, choose one of the SIP Sorcery dial plans available in the Source section of this site, copy it from the "raw view", go to the Dial Plans page in SIP Sorcery, click on default, and paste in the dial plan you selected, overwriting the short default script already there. Customize the sections of the dialplan marked accordingly. The script will not function correctly and you will not be able to make free outbound calls until you customize the required entries.<br>
<br>
If you've made it here, you should be all set. If you followed all the steps properly, you should be able to start your SIP client or pick up your ATA-connected phone and dial any number in the US for free. If you are unfamiliar with other SIP clients and SIP-compatible devices available to you, please refer to the original HOWTO document linked from this project's home page.<p>

NOTE: If you are unable to follow these steps and just can't seem to get outbound dialing to work, please see section 14 of the original Free Calling HOWTO document for  more detailed instructions, including screenshots of the setup process.