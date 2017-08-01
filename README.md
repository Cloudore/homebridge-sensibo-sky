# homebridge-sensibo-sky
[Homebridge](https://github.com/nfarina/homebridge) platform plugin for the Sensibo and Sensibo Sky
Original Plug-in: https://github.com/wailuen/homebridge-sensibo-sky

# Installation

1. Install homebridge using: npm install -g homebridge
2. Go into your node_modules folder, where the plug ins are stored.
3. Download this plugin using: "sudo git clone https://github.com/Cloudore/homebridge-sensibo-sky.git"
4. go into the plug in folder with "cd homebridge-sensibo-sky"
5. Install using "sudo npm install"
6. Update your configuration file. See sample config.json snippet below. 

# Configuration

Configuration sample:

 ```
"platforms": [
		{
			"platform": "SensiboSky",
			"name": "Sensibo",
			"apiKey": "YOUR_SENSIBO_API_ID",
			"timeLapse": 5,
			"ai": false,
			"hideHumidity": true			
		}
	],

```

Fields: 

* "platform": Must always be "SensiboSky" (required)
* "name": Can be anything (required)
* "apiKey": Sensibo API key, must be obtained from https://home.sensibo.com/me/api (required)
* "timeLapse": Time in seconds to recycle the status from Sensibo. Too frequent will result in many timeout from sensibo server. Default is 30s. (Optional)
* "ai": This fork does not support ai, keep it "False"
* "hideHumidity": true or false. True would move the humidity info into thermostat detail. Default is false. (Optional)

# Usage Notes

*Fan is disabled in this version, instead it is integrated inside the Thermostat module, but that means it will not appear in the Home.app
* This module modified from the original Sensibo and adopted for Sensibo Sky to improve the stability due 
to the constant ERRCONNECT from Sensibo server when there is too many request. Staggered update for each 0.5s each from timeLapse.
* The refresh is now splitted to the individual pods instead of all at one go to mininize error from the sensibo server.
* Had also resolved bugs on the fan and better error handling when Sensibo server does not respond. 


* All code adopted from pdlove and Waliuen.
