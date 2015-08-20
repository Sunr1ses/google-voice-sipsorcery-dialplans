# Introduction #

Localphone.com offers yet another way to extend your reach with Google Voice. They begin with free incoming calling to SIP-based VoIP phones, like sipgate or IPKall. Localphone sets itself apart however, in that they do not require you to have a VoIP phone or device when you travel internationally. Their service is fully capable of extending your GV number to standard landlines or mobiles in over 100 countries for low per-minute rates.

Not everyone who travels abroad can expect to have continuous solid 3G data or wifi coverage, so Localphone gives travelers the option of extending their Google Voice to a traditional in-country phone number assigned to a landline or a mobile.


# Integrating Localphone via the Standard Phone Network #

Google Voice forum user "d4rr3ll" (Darrell Taylor) is a Localphone employee, and posted the following instructions in the Google Voice forum. These instructions are not to be considered formal instructions from Localphone. Darrell found and documented a process that works, and wanted to share it for informational purposes only.

These instructions assume you have already signed up for a free Localphone account at https://www.localphone.com/register

**From Darrell:**

I've had a look at this and have figured a work around for the verification process, once done this will allow you to use the shared Localphone Direct Dial numbers with your GV account.

The trick is to be able to answer the call that asks you to verify the number, now the initial problem here is that the call verification call doesn't originate from your GV number, it's a Mountain View, CA number.  So all you have to do is add the number as one of 'My Numbers' to your Localphone account, get it to call one of you Direct Dial access number (which you have configured to forward to your Landline or Cell while you do the verification) and the punch in the digits it asks.  Once the number is verified you can then edit it to call whatever international number you want.  You also need to tweak your GV setting in order to get this to work, I'll list the steps I took below to make this work on my account.

  1. Add 650-265-1193 as one of 'My Numbers' on your Localphone account, ensure you only have this number on your account for the shortest period of time otherwise there is potential for someone else to end up using your Localphone account credit.  YOU HAVE BEEN WARNED

> 2. Add or edit one of your Localphone contacts to dial the phone your going to answer to verify the number, make a note of the Direct Dial number shown in red.

> 3. Add the Localphone Direct Dial number as a phone on your GV account and follow the verification process, you will be charged for the Localphone call to the phone you are using to verify your account.

> 4. REMOVE 650-265-1193 FROM 'My Numbers' ON YOUR LOCALPHONE ACCOUNT  I can't stress enough how important this is.

> 5. Add _your_ GV number as a number to 'My Numbers' on your Localphone account.

> 6. Edit your GV settings and enable 'Display my Google Voice number' in the 'Caller ID' section, this is important otherwise the presented caller id will be incorrect and the Direct Dial logic on LP will not work.  I think you can configure this at 'Group' level, but I'll leave that as an exercise for the reader to figure it out.

I think thats pretty much it, you should now have a verified Localphone Direct Dial number on your account.

I need to stress again how important it is to remove the 650-265-1193 from 'My Numbers' after you have verified the number, if you don't remove it then anyone else who is trying to verify their number will end up calling through **YOUR** account and this will come out of your credit.  Also if when you try to add this number to 'My Numbers', if you get the error message to say that the number already exists it likely that someone else is in the process of verifiying their account, so please be patient and play nice people :)

**Update**

It appears that Google are now presenting **your** GV number when verifying accounts again, this should make things a lot easier from now on and remove the need to add and remove the 650 number. (**Note:** This change was reversed after a month, but may return at any time.)

But, and this is a **big** but, they only seem allow you to add one instance of a phone across the whole of the platform, I have just tried to add a Localphone access number 914-371-5006 and the GV message popped up to say it was already in use on another GV account.  So it looks like the people who have got this setup already are the lucky ones, new users are going to have to use pot-luck to try and find access numbers that are not already in use, we currently have over 6000 access numbers in the US, so there are a few to go at before they run out.

**Disclaimer**
I work for Localphone and this is posted for informational purposes only, you use this information AT YOUR OWN RISK, myself and Localphone do not accept any responsibility for anything that might happen as a result of using this information.

# Integrating Localphone Using VoIP #

You are not required to use the chargeable features of Localphone when integrating with Google Voice. Just like Gizmo5, sipgate, and SIP Sorcery, Localphone will receive calls over VoIP via SIP and forward them free of charge to connected softphones.

Sign up for a free account as described above, and from your main page, click the VoIP link in the second row of menu buttons. Click the Submit button to add the VoIP feature to your account, also for free. Take note of your SIP credentials. **Note:** They are **not** the same as your web site credentials. Next, you need to forward calls to your Localphone account via SIP.

## Forwarding via IPKall ##

If you do not already have a Gizmo5 account, go to IPKall.com with your browser. Create a new account and choose SIP as the Account Type. Choose any area code they offer, it does not matter. Your SIP phone number is your SIP id that you wrote down earlier. Your SIP proxy is localphone.com. Enter a valid email address and select a unique password for the IPKall site. Do **NOT** enter your email password. You should receive a confirmation email from IPKall within 72 hours. Once you validate your request, you will receive your new phone number from the area code you selected at signup. Proceed with client configuration.

## Client configuration ##

To receive calls via VoIP, configure your SIP client to connect to your new VoIP-enabled Localphone account using the credentials given to you by Localphone. According to http://help.localphone.com/voip/devices/softphone/xlite you may configure your SIP client as follows:
```
Display Name: Localphone
User name: [SIP ID]
Password: [SIP Password]
Authorization User name: [SIP ID]
Domain: localphone.com
Proxy: proxy.localphone.com
```
## Integrating with Google Voice ##

Once your SIP client successfully logs into your Localphone account via SIP, you must now add your IPKall phone number to Google Voice. Log into Google Voice, choose Settings, Voice Settings, and click Add Another Phone. Enter the phone number assigned to you by IPKall, and choose Work as the type of phone.

Click Save and Google Voice will display a 2-digit number to enter for verification. Click Connect, and if your setup works, your SIP client softphone will ring. Answer the call and enter the 2-digit number Google Voice displayed for you. Google Voice should show the number as verified and ready for use.

## Making and receiving calls over VoIP without SIP Sorcery ##

With Google Voice properly configured to forward all incoming calls via SIP to your Localphone account either via Gizmo5 or IPKall, you are now able to receive unlimited calls via VoIP as well as place unlimited calls to all phones in the US and Canada. To place a call for free over VoIP, visit the Google Voice website and initiate a call using your IPKall (or Gizmo5) number as the phone you wish to use. Note that the Google Voice website automatically adjusts for mobile devices to allow for quick navigation. Once you enter or select a phone number to call on the GV website, Google Voice will call you via your SIP client softphone. Answer the call and you will be connected to the number you selected or entered on the web site. You **must not** enter phone numbers to call directly from your SIP client softphone if you wish to place calls for free. Any calls placed directly in your SIP client will incur charges by Localphone -- even to US-based numbers. Note that if Localphone charges a better rate than Google Voice to call an international destination, you may go ahead and enter the number directly into your SIP client and place the call. Similarly, if Google Voice offers a better rate to call an international destination, dial via the Google Voice website to obtain their rate.

## Making and receiving calls over VoIP using SIP Sorcery ##

Since Localphone's VoIP capabilities mimic those of sipgate, you may follow the instructions under "Original content" on the sipgate wiki page at this site. Just be sure to enter your Localphone credentials and configuration details when adding Localphone to your list of SIP Providers.