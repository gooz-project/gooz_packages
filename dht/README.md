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
* Also, dht listen command accepts some parameters:
```shell
dht listen [NAME_OF_DHT_SENSOR] --[PARAMETER_KEY] [PARAMETER_VALUE]
```
- Parameters:
    - --file [FILE_NAME]
        - If this parameter exists, the readed value will be written in the given `[FILE_NAME]`
        - `[FILE_NAME]` format can be directly file name or file name with path
            - listen_values.txt
            - /user_files/listen_values.txt
    - --date [DATE_BOOL]
        - Default value of `[DATE_BOOL]` is `1`
        - `[DATE_BOOL]` can be 1 or 0
        - If `[DATE_BOOL]` 1, the readed value will be written with date
    - --loop [LOOP_COUNT]
        - Default value of `[LOOP_COUNT]` is `-1` that means, it will read until stopped manually.
        - If `[LOOP_COUNT]` is bigger than 0, the number of reads will be the given number.
    - --delay [SLEEP_TIME]
        - Default value of `[SLEEP_TIME]` is `1`
        - `[SLEEP_TIME]` can be any float number.
        - Listen command waits as `[SLEEP_TIME]` (unit = second) between two read operations.
    - --end [END_CHARACTER]
        - Default value of `[END_CHARACTER]` is `“\n”`
        - `[END_CHARACTER]` can be any character
        - Listen command prints given `[END_CHARCTER]` after readed value in files.
    - --measure [MEASURE_TYPE]
        - Default value of `[MEASURE_TYPE]` is `both`
        - `[MEASURE_TYPE]` can be `both` `temp` or `hum`
