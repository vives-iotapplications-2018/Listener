# TTN Listener

## inleiding

The sensor sends data to the TTN, the TTN wil be filtered and generate a JSON String.
This Json String will send with the integrated MQTT of The things network to the listener (this project).
This Json string wil send all the incoming data filtered to the HTTP

![roadmap](/pictures/roadmap.jpg)

## Installation

`git clone git@github.com:Projectwerk2-2018/smart-campus-ttn-backend.git`

Installing the dependencies:

`npm install`

## Configuration

Make a copy of the `settings.example.json` file and name it `settings.json`. This can be done with the following command as well: `cp settings.example.json settings.json`.

Then update the changes in the file according to your setup.

```javascript
{
	"ttn":{
		  "appId": "TEST",
		  "accessKey": "ttn-account-v2.TEST"
	  },
	  "http":{
			  "host": "localhost",
			  "port": 8000,
			  "path": "/"
	  }
} 

```

## Running the application

`node server.js`

or

`npm start`

## testing the application
set the localhost_test.js file in a new project.

run the project

`node localhost_test.js`

if the hardware is online you will have automaticly respons 

other whise you can *simulate uplink*

test with payload `00D71B0049`

![payload](/pictures/payload.png)

## agendapunten

SIMULATIE => HTTP

1.  recieve fake data from ttn to server.js

sending fake data and recieve it in the console.
to start the console: `node server.js`

2.  setting.json file aanmaken and ignore on github

yo need a .gitignore file to not publisch you accas key and id

3.  decode incoming massage and retrieve payloud.

the default uplink is:

```shell
{ app_id: 'TEST',
  dev_id: 'fake_device',
  hardware_serial: 'TEST',
  port: 1,
  counter: 0,
  payload_raw: <Buffer aa>,
  metadata: { time: '2018-03-07T09:15:37.47879368Z' } }
```

you need to collect only the payload_raw data.

```
{payload_raw: <Buffer aa>}
```

3.  Convert the payload_data to a Json file than can be include in the backand.

* talk to Steve Trap to know what he needs as input.
* talk to the electornic peaple to know what data will come in.

4.  send you incoming data to the backand

* talk to Steve Trap how to do this the best way.

5.  LoRaWan downlink. vanaf backand terug naar TTN

# referenties

https://github.com/TheThingsNetwork/node-app-sdk/blob/master/examples/es5/data.js
