# Cellphones

## Any?

Status of Call Forwarding options -- verified on AT&T iPhone

### show IMEI, EID, MEID
```text
*#06#
```

-
- [ ] Make this into below into a table!

||| Action ||| Mobile Carrier ||| How |||
| Show Data usage | | |
| Check Acct balance | | |


## AT&T Wireless

### Show data usage

```text
*3282#
```
You'll receive a text message that contains data usage.

### Current account balance
```text
*225#
```
You'll receive a text message that contains account balance data.


## Use Google Voice to replace any phone's voicemail service

Reference: https://support.google.com/voice/answer/165656
"Send your mobile phone calls to Google Voice voicemail"

### AT&T Wireless

#### Enable
Enter the following 3 commands one at a time on your phone’s keypad, tapping "send" or "call". Wait until you receive confirmation the change worked.

Call forward if unanswered:
```
*61*<Google Voice number>#
```
Call forward if unreachable:
```
*62*<Google Voice number>#
```
Call forward if busy:
```
*67*<Google Voice number>#
```

#### Disable

Call forward if unanswered:
```
##61#
```
Call forward if unreachable:
```
##62#
```
Call forward if busy:
```
##67#
```


### Verizon Wireless

Verizon Wireless: via website or the method below

#### Enable
```text
*71<Google Voice number>
```
 on your phone’s keypad, wait for the confirmation stutter tone, then hang up.

#### Disable
```
*73
```
on your phone’s keypad, wait for the confirmation stutter tone, then hang up.



# Verizon - all codes
```
Code to call: 	Use when you need to:
#BAL (#225) 	Check your balance
#DATA (#3282) 	Check your data usage
#MIN (#646) 	Check your minutes
#PMT (#768) 	Make a payment
#ROAD (#7623) 	Request roadside assistance
#UPG (#874) 	Check your upgrade information
#832 	Place a test call
*611 	Call Verizon Customer Service
*67 + 10-digit phone number 	Block Caller ID for a single call
*71 + 10-digit phone number 	Forward unanswered calls (mobile phone will ring first)
*72 + 10-digit phone number 	Forward all calls immediately (mobile phone won’t ring)
*73 	Stop forwarding calls
*82 + 10-digit phone number 	Unblock Caller ID for a single call
*86 	Check your voicemail
```
Source: https://www.verizon.com/support/pound-star-codes/


# T-Mobile - all codes
```
Short code 	What it does
#BAL# (#225#) 	Provides account balance and last payment
#BNG# (#264#) 	Check the status of Binge On™
#BOF# (#263#) 	Turn off Binge On
#BON# (#266#) 	To on Binge On
#FAM# (#326#) 	Check Family Allowance usage

#MIN# (#646#)
	Check minute usage
#MSG# (#674#) 	Check message usage
#WEB# (#932#) 	

Check data used, data plan, and expiration date

Use the T-Mobile app for the most up-to-date information
#NUM# (#686#) 	Display your phone number
*PAY (*729) 	Allows you to pay over the phone
#PWD# (#793#) 	Reset voicemail password
#PWO# (#796#) 	Turn the voicemail password on or off
#ROF# (#763#) 	Turn off international data roaming

#RON# (#766#)
	Turn on international data roaming
*#06# 	Display device IMEI number
*#9999# 	Check software version (Motorola and Samsung)
*#0000# 	Check software version (Nokia)

 
Call services

Change the way you use your Calling services and voicemail.
Short code 	What it does
##004# 	Cancel call forwarding to voicemail (prevents new voicemail messages)
**21*1+PhoneNumber# 	Turn on unconditional forwarding (CFU) to a number (prevents calls to your number)
##21# 	Turn off unconditional forwarding
#31#1+PhoneNumber 	Show name and number on outgoing calls
*31#1+PhoneNumber 	Hide name and number on outgoing calls
**61*1+PhoneNumber# 	Turn on forwarding if no reply (CF NRY) to a number (unanswered calls ring to alternate number)
##61# 	Turn off forwarding if no reply
**62*1+PhoneNumber# 	Turn on when not reachable (CF NRC) (unanswered calls ring to another number when device is off or out of signal range)
##62# 	Turn off call forwarding when not reachable
**67*1+PhoneNumber# 	Turn on call forwarding when busy (CFB) (occurs if receiving a call while dialing out)
##67# 	Turn off call forwarding when busy
**61*18056377243**seconds# 	

Change call forwarding delay time. Choose a 5, 10, 15, up to a 30-second delay. For example, dialing **61*18056377243**10# would be a 10-second delay.
*43# 	Turn on call waiting
#43# 	Turn off call waiting
*671+PhoneNumber 	Blocks outgoing Caller ID on a per-call basis. This doesn't restrict your information when you dial certain business numbers, including 911, 900 numbers, or toll-free numbers.
#432# 	Caller ID status check
#436# 	Turn on inbound Caller ID name display 
#437# 	Turn off inbound Caller ID name display

 
Prepaid

Check your Prepaid account balance details, Refill your prepaid account, and manage Unlimited video streaming with Binge On®.
Short code 	What it does
*ADD (*233) 	Call the Refill Center
#BAL# (#225#) 	Check account service cycle
#999# 	Check account balance and minutes remaining
#WEB# (#932#) 	Check web usage
#BNG# (#264#) 	Check the status of Binge On
#BOF# (#263#) 	Turn off Binge On
#BON# (#266#) 	Turn on Binge On

```
Source: https://www.t-mobile.com/support/plans-features/self-service-short-codes

