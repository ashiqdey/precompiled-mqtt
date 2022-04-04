![mqtt.js](https://raw.githubusercontent.com/mqttjs/MQTT.js/137ee0e3940c1f01049a30248c70f24dc6e6f829/MQTT.js.png)
=======


## Precompiled version of mqtt.js for browser
This package is a prebuild version of mqtt [mqtt (npm)](https://www.npmjs.com/package/mqtt) [Github](https://github.com/mqttjs/MQTT.js)
For using the mqtt in react we have to build using webpack which thorws dozens of error in webpack 5 and due to varying system environment. So the goal of this package is to able to use the official mqtt package directly without any additional work. Also while deploying our react project in AWS amplify do face lot of issue in setting up build configs so using this package those issues will be solved. 

This package had been tested only with react 17. But it should work with other frontend library as well.
