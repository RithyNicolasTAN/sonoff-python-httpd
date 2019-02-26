# sonoff-python-httpd

Make use of your sonoff smart switches without flashing them via the cloud APIs, this should work in Python 2 or Python 3.

This project is heavily inspired (read: almost entirely borrowed) by the work  : 
- Peter Buga : https://github.com/peterbuga/HASS-sonoff-ewelink
- lucien2k : https://github.com/lucien2k/sonoff-python

My objective is to make a http script

## Modules requirements
- request
- websocket
- websocket-client

## Configuration

Configuration is simple and basically passed to the class when you instantiate it. Username is either the email address you use to log in to Ewelink, or your phone number with the country code in front.

> **login** - The email address or phone number you signed up with on Ewelink. Preface phone number with the country code

> **password** - Your password to Ewelink.

> **server** - The API region you use, valid ones are apparently 'us', 'eu' and 'cn'

> **localhost** - 

> **port** - 

## Launch

python (or python3) sonoff-python-httpd.py

## Usage

> **http://localhost** : Get json data for all devices

> **http://localhost/status/deviceid : Get status for device (0 = off; 1 = on)

> **http://localhost/on/deviceid : Turn ON device and get status after operation (1 = on if sucessfull)

> **http://localhost/off/deviceid : Turn OFF device and get status after operation (0 = off if sucessfull)

## Support

I have tested in Python 2 and Python 3, however as we all know there may be some library weirdness.

## Docker configuration

To write

## Jeedom Integration

Use plugin "Script"
To write...

## Troubleshooting

### Ewelink registration for 4 channel switches
The Sonoff switches have one of the most non-intuitive installation processes I have encountered. For registering my 4 channel switch I had to:
* Hold one of the buttons until it flashed quick, quick, slow.
* Hold a second time until it rapidly flashed in a constant pattern. I did not see the ITEAD-xx access point until it rapidly flashed.
* Once it is rapidly flashing, connect to the ITEAD-xx network.
* Choose the Compatible Pairing Mode (AP) option, then press Next. (This looks like a help page, but it is actually a fourth option (and the one you want!!)).
* Follow the onscreen instructions.
