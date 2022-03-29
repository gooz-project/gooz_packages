# DHT Sensor Package for GoozOS
This package provides temperature and humidity measure with DHT11 and DHT22
## Package Install
```shell
pkg install dht
```
## Package Using

### Help
```shell
dht help
```
Shows all commands
```shell
dht help [COMMAND_NAME]
```
Shows special help for command_name


### Defining a DHT sensor
```shell
dht register --name [DHT_SENSOR_NAME] --pin [DHT_SENSOR_PIN] --type [DHT_SENSOR_TYPE]
```
* DHT sensor type must be 11 or 22.
* All of these variables must be entered.
### Updating Parameter(s) of a Defined DHT SENSOR
```shell
dht update [NAME_OF_UPDATING_PIN] --pin [NEW_DHT_SENSOR_PIN]
``` 
* You can update multiple parameters same time: 
```shell
dht update [NAME_OF_UPDATING_SDCARD] --name [NEW_DHT_SENSOR_PIN] --type [NEW_DHT_SENSOR_PIN]
```

### Deleting a Defined DHT Sensor
```shell
dht delete [NAME_OF_DELETING_DHT_SENSOR]
```

### Show Defined DHT Sensors
```shell
dht show
```
* You can show specific pin with specific parameter(name, pin, type)
```shell
dht show name:[WANTED_PIN_NAME]
```

### Measuring Temperature and Humidity of Defined DHT Sensor
``` 
dht measure [NAME_OF_DHT_SENSOR]
```
* Prints the current temperature and Humidty of the given DHT Sensor
### Listening Temperature and Humidty of Defined DHT Sensor
```shell
dht listen [NAME_OF_DHT_SENSOR]
```
* This command will prints the current temperature and humidty of the given pin every 1 second
* Also listen command can take more arguments:
```shell
dht listen [NAME_OF_DHT_SENSOR] [MEASURE_TYPE] [LISTEN_SLEEP_TIME]
```
* The measure type value can be temp, hum or both. Default value: both
* Also listen sleep time can given as second. Default value: 1
