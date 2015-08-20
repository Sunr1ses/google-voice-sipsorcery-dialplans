Users of Google Voice are patiently waiting for Google to restore full SIP integration. Until that happens, users are able to sign up for free accounts at a few web sites, glue them together with some scripts, and enjoy free unlimited SIP calling with Google Voice today.

# Background #

SIPSorcery.com is a site that specializes in managing and routing SIP-based Voice Over IP (VOIP) phone calls. New user accounts are created with minimal functionality, but their usefulness can be enhanced through the use of scripts written in Ruby. The scripts we distribute here on this site allow SIP Sorcery users to convert Google Voice into a full VOIP service. This includes free wifi calling from anywhere in the world on certain smartphones to US and Canadian phone numbers and creating free home phone lines using analog telephone adapters (ATAs) such as the Linksys PAP2T-NA.

This project began as a publicly shared document describing how to achieve free calling with Google Voice. The link to that document is featured in the links section to the left. Also shown is the original thread in the Google Voice Help Forum where the original document was announced and discussed.

The background and configuration steps in the HOWTO have been replicated in the wiki on this site. If you visit the Wiki section and find the pages out of order, please click "Page Name" and then "Sort Up".

Please visit the Issues tab to report on issues you may be experiencing when attempting to follow the instructions found on this site. It is very difficult for us managing this site to find and keep track of everyone's individual issues as they pop up in the forums, and using the Issues tab lets us give each issue the individual attention it deserves. Please try to read other users' issues that are similar to yours, and participate as appropriate but also to avoid hijacking another open issue.

Thanks for reading, and welcome!

# Let's Get Started! #

There are a few different places you want to go to get started, depending on your skill level and experience.

## With a SIP Client ##

If you already know that you want to use Google Voice with a SIP client installed on a smartphone app or an ATA, take a look first at wiki page 5, the [VoIP Calling Quick Start](http://code.google.com/p/google-voice-sipsorcery-dialplans/wiki/05_VOIP_Calling_Quick_Start) page. Once you are ready for more details, check out wiki pages 6-10 for a variety of options. If you are unable to sign up for a free account at SIP Sorcery, check out the wiki pages for [Localphone](http://code.google.com/p/google-voice-sipsorcery-dialplans/wiki/06_Google_Voice_Integration_with_Localphone), [sipgate](http://code.google.com/p/google-voice-sipsorcery-dialplans/wiki/07_SIP_Sorcery_Integration_with_sipgate), [IPComms](http://code.google.com/p/google-voice-sipsorcery-dialplans/wiki/09_SIP_Sorcery_Integration_with_IPComms) and [pbxes](http://code.google.com/p/google-voice-sipsorcery-dialplans/wiki/10_Sipdroid_Integration_with_PBXes) for ideas on how to get going without a SIP Sorcery account. Regardless of how you connect with a SIP client, you still have to prepare your SIP connection, and any of the pages above will help.

If you have an Android device and want a very easy way to get going, check out wiki page 10, [Sipdroid Integration with PBXes](http://code.google.com/p/google-voice-sipsorcery-dialplans/wiki/10_Sipdroid_Integration_with_PBXes). Note that the procedure shown on that page requires an Android device, but leaves you with a standard free SIP account which is compatible with a wide variety of SIP clients and devices. It also does not require a SIP Sorcery account.

## Without a SIP Client ##

If you need to take things more slowly or are just interested in using Google Voice with a regular landline phone or cellphone (not a smartphone) within the US, then start with wiki page 1, Introduction before moving on to wiki pages 2 & 3 to learn how to place free calls with your landline or regular cellphone.

# New Content - pbxes #

Attention: If you are unable to sign up for a free account at SIP Sorcery, I found clear, concise instructions for integrating Google Voice as a SIP client to pbxes.org. Not sure how I missed it for almost a year, but an excellent YouTube video was published last August and the instructions still appear to be pretty close to dead on.

I only needed to make minor tweaks in order to make this work with a SIP client on an unsubscribed phone. The good news is that pbxes uses a different dialout mechanism, so sipdroid dialing via pbxes worked great, even when I couldn't dial out at SIP Sorcery.

Please see the wiki page [10](http://code.google.com/p/google-voice-sipsorcery-dialplans/wiki/10_Sipdroid_Integration_with_PBXes) for all the details.

# Unable to dial out? #

If you are experiencing the "rnr se key" issue and are unable to dial out, this process to clear the error has worked for a number of us:

  1. Make absolutely sure that your inbound calling is working by calling your inbound SIP gateway number. Your SIP client attached to SIP Sorcery should ring.
  1. Visit https://www.google.com/accounts/DisplayUnlockCaptcha and enter the CAPTCHA.
  1. Place a call using your SIP client logged into your SIP Sorcery account within 10 minutes.

That should do it. This has been reported to work on multiple accounts and for multiple users.

# Disclaimer #

The code and support provided at this site is in no way related to, provided, sanctioned or supported by Google. We have no connection to Google, sipgate, SIP Sorcery, pbxes or any other service provider mentioned herein other than as satisfied users. Please refer to the appropriate support forums if you have specific questions related to those services.

We do not alter or enhance Google Voice functionality. What we do provide and support here are scripts designed to enhance your experience when using SIP Sorcery, primarily with the goal of adding a SIP-compatible true VoIP phone line to your Google Voice account. Our instructions will help you create a new managed phone in Google Voice, separate and independent of any traditional phone lines you may already have configured in your account, that allows you to make and receive calls using only an Internet connection and a SIP client installed on a capable and properly configured device.