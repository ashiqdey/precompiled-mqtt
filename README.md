![mqtt.js](https://raw.githubusercontent.com/mqttjs/MQTT.js/137ee0e3940c1f01049a30248c70f24dc6e6f829/MQTT.js.png)
=======


## Precompiled version of mqtt.js for browser
This package is a prebuild version of mqtt [mqtt (npm)](https://www.npmjs.com/package/mqtt) [Github](https://github.com/mqttjs/MQTT.js)
For using the mqtt in react we have to build using webpack which thorws dozens of error in webpack 5 and due to varying system environment. So the goal of this package is to able to use the official mqtt package directly without any additional work. Also while deploying our react project in AWS amplify do face lot of issue in setting up build configs so using this package those issues will be solved. 

# Important
Use lastest version or precompiled-mqtt@4.3.12 which is the build of mqtt@4.3.7 please dont install any version prior to 4.3.12 those are buggy and not well tested.


## Why this package?
Just to get rid of [this build process for react](https://github.com/mqttjs/MQTT.js#react)
```
npm install -g webpack                    // Install webpack globally
npm install mqtt                          // Install MQTT library
cd node_modules/mqtt
npm install .                             // Install dev deps at current dir
webpack mqtt.js --output-library mqtt     // Build
```


This package had been tested only with React 17. But it should work with other frontend library as well.

NOTE : This package is replacement of [mqtt@4.3.7](https://www.npmjs.com/package/mqtt)

# Installation
```
npm i precompiled-mqtt
```

# Example
This is a piece of peudo-code, please raise a issue if you find any
```
import mqtt from "precompiled-mqtt";

// mosquitto test broker
const URL = "mqtt://test.mosquitto.org:8081";

// Local broker
const URL = "ws://192.168.43.xx:1234";

const client = mqtt.connect(URL);

client.on('connect', () => {
    console.log("CONNECTED to broker");
});


const onMessage = (callBack) => {
    client.on("message", (topic, message, packet) => {
        callBack(JSON.parse(new TextDecoder("utf-8").decode(message)));
    });
}
```

For original documentation please refer to the  [official github repo of mqtt.js](https://github.com/mqttjs/MQTT.js#readme)

