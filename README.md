# Netatmo
Weather from Netatmo on the Raspberry Pi 5

This is my first project, so I believe it will be not completed due to lack of knowledge .

**Target**
On the  Raspberry Pi 5 with LCD display show  all useful information from Netatmo Weather Station like:
"time_utc"

"Temperature (OutIndoor)"

"Temperature (Indoor)"

"CO2"

"Humidity"

"Noise"

"Pressure"

"Rain"

"battery_percent"

  More info aboout station: https://shop.netatmo.com/pl-pl/weather/accessories/fullweather-stationpack

 This project is  required, because similar project does not work due to Netatmo change their API server which not accept any more password grant for authentication :
 https://github.com/Gulivertx/cbatmo/tree/master

**Useful information**

Instruction from product page - the biggest challenge Authentication :https://dev.netatmo.com/apidocumentation/oauth

Quickly send and test any type of API request via: reqweb.postman.co

Documentation getmeasure: https://any-api.com/netatmo_net/netatmo_net/docs/public/getmeasure

**What I know 16.06.24**
Connection to api is possibile required:
1) Create api on that link:  https://dev.netatmo.com/
2) To connect to the Api required created something like this ( tested via postman-works):
 const request = require('request');

 const clientId = 'XXXXXXXXXXXXXXXXXXXXXXXX';

const clientSecret = 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx';

const accessToken = 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx';

const type = 'CO2,Temperature';

const scale = '30min';

const deviceId = 'NN:LL:NN:LL:NL:NN'; // Replace with your Netatmo device ID

 const options = {
    url: `https://api.netatmo.net/api/getmeasure?device_id=${deviceId}&access_token=${accessToken}&type=${type}&scale=${scale}`,
    method: 'GET',
    headers: {
        'Authorization': `${accessToken}`,
        'Content-Type': 'application/json'
    }
}
