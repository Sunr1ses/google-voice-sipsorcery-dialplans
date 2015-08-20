# Before we get started #
In the time since this website was created, our resident script writer Mike Telis has helped Aaron at SIP Sorcery develop a new, bare bones approach to adding a SIP extension to Google Voice. That approach is covered in wiki page 5, VoIP Calling Quick Start. Assuming you already have a SIP Sorcery account or are willing to sign up for a paid account, the approach outlined on wiki page 5 should be enough for just about anyone looking to create a SIP extension on Google Voice.

Please continue reading this page if you are using SIP Sorcery (and not the new sipdroid/pbxes approach) and require the extended functionality available in a full diaplan script, such as "short codes" used for calling frequently dialed numbers or SIP numbers that just can't be called from a standard telephone keypad.

# Modifying your dialplan #
The very top of the dial plans contain the "Mandatory Entries" section. First, there are between four and six pieces of information that you will need to provide, depending on the dialplan you choose to use. The four details common to both dial plans are:<p>

<ol><li>Your Area Code<br>
</li><li>Your Google account in full email address form (typically "user@gmail.com")<br>
</li><li>Your Google account's password<br>
</li><li>The 10-digit phone number assigned to you by sipgate or ipkall.</li></ol>

If you choose to use the Complex Dial Plan, you have two other changes that are required:<br>
<br>
<ol><li>The 10-digit phone number assigned to you by Gizmo5. This will be a number in area code 747.<br>
</li><li>Your time zone.</li></ol>


IMPORTANT: If you are disconnecting your home phone service and do not have a cellphone, be advised that Google Voice does not provide 911 service. You should take a minute to call your emergency services center ON A NON-EMERGENCY NUMBER and ask them for the best alternative number to call if you don't have 911 service.<p>

<b>URGENT NOTE:</b> It is always best to call 911 from a live phone line provided by the phone company. Your second best option is your cellphone, preferably one with GPS functionality. Your very last option should be to use Google Voice to call the alternate number provided to you by your emergency services center. They will not have automatic addresses or GPS coordinates, so they will have the least amount of information available if you call during an emergency. They will also typically answer 911 calls first so you may not get an immediate response when it is most urgently needed. Sipgate does offer 911 service for a low monthly fee, and they will transmit your registered address to the authorities should you need to call 911. We have not updated the dialplans to handle routing 911 through sipgate at this time.<p>

After the mandatory settings section in each dial plan is the optional speed dial directory. This function has two benefits. First, it brings customizable "short codes" to standard phones. This allows numeric codes to be dialed and have those codes interpreted to trigger a connection to a specific destination. For example, a user can create "extensions".<p>

A popular use for the speed dial directory is to listen to podcasts collected by podcast aggregator Podlinez. They collect thousands of regularly updated podcasts and link them to phone numbers. By calling the assigned phone number, the user will immediately hear the latest episode of the associated podcast. Podlinez takes the extra step, however, of making each and every phone line also available via SIP. This means that SIP Sorcery can be configured to call any of those numbers directly over SIP instead of using Google Voice to call into Podlinez via a standard phone line. And since the speed dial directory supports translating short codes to other SIP-accessible phone lines, users are free to choose any number of podcasts from the Podlinez directory and add them to their speed dial list.<p>

For example, the NPR News top stories podcast is updated hourly and available to all phones at 1-650-644-1952. Podlinez also makes that phone number available via SIP at "6506441952@podlinez.com". Instead of dialing the entire number or creating an entry in the address book for each device attached to your SIP Sorcery account, a "short code" number can be added to the custom speed dial directory at the top of the script. As soon as the script has been updated, all attached devices can dial the short code and hear the headlines. Since 677 spells "NPR" on a standard telephone keypad, the short code can be added to the speed dial directory with this simple line placed in the middle of the directory:<p>

<blockquote>'677' => '6506441952@podlinez.com',  # NPR News Summary (677 = "NPR")<p></blockquote>

Again, all phone numbers listed in the Podlinez directory can be added to the speed dial directory by creating an entry formatted like the one above. This is not required as users are still free to call the traditional phone lines to hear the podcasts.