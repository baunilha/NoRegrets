## ITP DWD - Using Remote APIs

Download code. Open code directory in Terminal.

#### #1 Create virtualenv

	virtualenv venv


#### #2 Install requirements

In your code directory run the command below to install new requirements.

	. runpip

or

	. venv/bin/activate
	pip install -r requirements.txt


2 new libraries we're using in this example, Twilio and Requests


#### #3 Start server

Start server

	. start

or 

	. venv/bin/activate
	foreman start

-----------


## Getting Started with Remote APIs

### Foursquare API

demo **/fsq**

This is a demo of passing a latitude and longitude to Foursquare Venue Search to get the venues nearby.

You will need the following for the demo

[Register a new application with Foursquare's developer site](https://foursquare.com/developers/apps)

Take the Client ID and Client Secret and put them inside your .env file
  
**.env**

	FOURSQUARE_CLIENT_ID=XXXXXXXXXXXXXXXX
	FOURSQUARE_CLIENT_SECRET=XXXXXXXXXXXX


**app.py** will use the environment variables to make the request to Foursquare.

**IMPORTANT** Heroku needs your Foursquare client information too, we need to add new config variables to your app.

**In your code directory in Terminal run,**

	heroku config:add FOURSQUARE_CLIENT_ID=XXXXXXXXXXXXX 
	heroku config:add FOURSQUARE_CLIENT_SECRET=XXXXXXXXXXXXXX


### Set up Google
Get your own Google API Key here [https://code.google.com/apis/console/b/0/](https://code.google.com/apis/console/b/0/).

Put the API Key in the Javascript, in the fsq.html template file.

	<script type="text/javascript" src="https://maps.googleapis.com/maps/api/js?key=YOUR_KEY_HERE&sensor=false"></script>

----------------

## Twilio demo

demo /twilio

### Getting Twilio Account

* Register [https://www.twilio.com/try-twilio](https://www.twilio.com/try-twilio).
* Verify phone number with access code.
* Pick a phone number.
* Poke around all their API endpoints, make and receive calls, make and receive SMS.

When you are registered locate your your Account SID and Auth Token here,[https://www.twilio.com/user/account](https://www.twilio.com/user/account) and add them to your .env file

**.env**	

	TWILIO_ACCOUNT_SID=xxxxxxxxxxxxxx
	TWILIO_AUTH_TOKEN=xxxxxxxxx
	TWILIO_PHONE_NUMBER=+XXXXXXXXX

Now let's add the Twilio account variables to Heroku.

**In your code directory in Terminal run,**

	heroku config:add TWILIO_ACCOUNT_SID=xxxxxxxxxxxxxx
	heroku config:add TWILIO_AUTH_TOKEN=xxxxxxxxxxxxxx
	heroku config:add TWILIO_PHONE_NUMBER=+XXXXXXXXX


