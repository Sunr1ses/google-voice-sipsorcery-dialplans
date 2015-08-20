# Background #

IPKall is a free, bare-bones system that forwards all inbound phone calls to a SIP provider you specify when you signup. They do not offer a public SIP server, so you must still sign up for an account elsewhere or host your own with Asterisk or its many derivatives. Normally, this would be SIP Sorcery, but in their absence other options exist, such as Localphone.com or pbxes as shown on [this](http://www.voip-info.org/wiki/view/Virtual+PBX+providers) site.

All support comes from community-led forums, so consider this fact when deciding which inbound SIP gateway you wish to use with Google Voice.

# Let's Get Started #
**Note:** In order to use SIP Sorcery as intended in this context, be advised that you must enter your Google Voice userid and password **unencrypted** on a publicly-accessible system. SIP Sorcery takes care to ensure the privacy and security of your private information, but it is up to you to consider the risks involved in storing those details on a system not controlled by you and the implications of your Google account details potentially being exposed should the server be compromised.

At this time, it appears sipgate, a SIP gateway provider we have recommended for use with Google Voice in the past, now indicates that they are unable to continue offering their service to new users. Since we only need inbound calls to be converted to SIP calls, we are able to replace sipgate with any provider capable of receiving calls via standard phone numbers and forwarding them to SIP clients or other SIP servers. One such alternative to sipgate is IPKall.<p>

In order to enable 24x7 free calling for Google Voice and IPKall users using just a SIP client, follow these simple steps to select and use a dialplan available on this site.<p>

1. Sign up for a free account at SIPSorcery.com.<br>
<br>
2. Sign up for a free account at ipkall.com.<br>
<br>
<ul><li>Make sure you choose SIP as the type of account.<br>
</li><li>Choose any area code from the list.<br>
</li><li>Enter the username you selected at SIP Sorcery as your SIP phone number.<br>
</li><li>Enter sipsorcery.com as the proxy server.<br>
</li><li>Enter your email address as requested, but do not use the same password you use for your email provider.<br>
</li><li>Leave the ring length at the default.<br>
</li><li>Enter the "human check" words and click Submit.</li></ul>

You will receive an email asking you to confirm your signup at IPKall. Once confirmed, you will then receive a standard (PSTN) telephone number that has been assigned to you. Any phone calls received on that PSTN number will now be forwarded to your SIP Sorcery account.<p><p><b>Note: This means you do not need to register your IPKall account in the SIP Providers at SIP Sorcery. All calls will automatically be forwarded to SIP Sorcery.</b><p>

3.  Configure your SIP client, SIP-compatible softphone or SIP-compatible ATA to login to your SIP Sorcery account. Check the "SIP Accounts" page of your SIP Sorcery account and make sure an entry appears in the "SIP Bindings" list at the bottom of the page.<p>

4.  Use a phone to call your new IPKall number and make sure the phone attached to your SIP Sorcery account rings. Answer the call and make sure you can hear sound in both directions.<p>

5.  Log into Google Voice, click Settings, Phones, and add your new IPKall phone number as a new managed phone. Google Voice will display a two digit number on your screen. Click Connect and Google Voice will call your IPKall number and ask you to enter the code displayed. Once you successfully add the new line, make sure it is checked on your Google Voice phone list.<p>

Note: You are now ready to receive inbound calls to your Google Voice number for free. You may also enter phone numbers on the Google Voice website and select your IPKall number as the phone you wish to use to make free outbound calls. There is one last step required to enable 24x7 free unlimited outbound dialing from your SIP-compatible softphone or standard telephone attached to your SIP-compatible ATA.<p>

<h1>Choose your dialout method</h1>

At this point, you must now choose how you plan to make outbound calls from SIP Sorcery. You may choose the "Google Voice Recipe" method or you may choose to install a full outbound dialplan.<br>
<br>
<h2>Google Voice Recipe</h2>
Note: Please see wiki page 5, VoIP Calling Quickstart for more details. Here are the steps required to finish the setup:<br>
<br>
1. Go to the SIP Providers page on SIP Sorcery and click Add<br>
2. Choose Google Voice as the type of provider<br>
3. Enter "MyGoogleVoice" as the provider name<br>
4. Enter your Google Voice id and password where requested<br>
5. Enter your IPKall phone number as the callback number<br>
6. Make no additional changes. Click Save.<br>
<br>
You are now configured for inbound and outbound calling via SIP and may now configure your ATA or other SIP client with you SIP Sorcery username and password.<br>
<br>
<h2>Original dialplan approach</h2>
1. Select one of the SIP Sorcery dial plans on the Source tab of this site. If you are new to this process, we recommend copying the Simple Dial Plan described in Section 11. Be sure to click "Raw View" at the bottom right corner of the screen.<br>
2. Highlight and copy the chosen plan to the clipboard.<br>
3. Return to SIP Sorcery, go to the Dial Plans page, click on default, and paste in the dial plan you selected, overwriting the short default script already there.<br>
4. Customize the portions of the dialplan as described in the comments located within the script. The script will not function correctly and you will not be able to make free outbound calls until you make the required customizations.<br>
5. Click Update when you have finished making the required changes.<p>

<h3>Optional</h3>
If you are planning to use your new SIP phone line with a smartphone, it is a good idea to learn how to use the Google Voice website for mobile devices. You will need to dial this way if your SIP Sorcery account is suddenly unable to dial out.<br>
<br>
1. Log into the Google Voice website from your smartphone<br>
2. Choose "Settings" and select your IPKall phone number as "This phone's number"<br>
<br>
<h1>That's It</h1>
If you've made it here, you should be all set. If you followed all the steps properly, you should be able to start your SIP client or pick up your ATA-connected phone and dial any number in the US or Canada for free.