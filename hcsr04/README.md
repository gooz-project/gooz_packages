# HCSR04 Sensor Package for GoozOS
This package provides measuring distance with HCSR04 sensor 
## Package Install
```shell
pkg install hcsr04
```
## Package Using

### Help
```shell
hcsr04 help
```
Shows all commands
```shell
hcsr04 help [COMMAND_NAME]
```
Shows special help for command_name


### Defining a HCSR04 sensor
```shell
hcsr04 register --name [HCSR04_SENSOR_NAME] --echo [HCSR04_ECHO_PIN_NUMBER] --trig [HCSR04_TRIG_PIN_NUMBER] --unit [MEASURE_UNIT] --echo_timeout [ECHO_TIMEOUT]
```
* `[MEASURE_UNIT]` unit can be `cm` `mm` or `inch`. Default value is `cm`
* Default value of `[ECHO_TIMEOUT]` is `20000`
### Updating Parameter(s) of a Defined HCSR04 SENSOR
```shell
hcsr04 update [NAME_OF_UPDATING_PIN] --pin [NEW_DHT_SENSOR_PIN]
``` 
* You can update multiple parameters same time: 
```shell
hcsr04 update [NAME_OF_UPDATING_HCS04] --name [NEW_HCSR04_SENSOR_NAEM] --trig [NEW_HCSR04_TRIG_PIN]
```

### Deleting a Defined HCSR04 Sensor
```shell
hcsr04 delete [NAME_OF_DELETING_HCSR04_SENSOR]
```

### Show Defined HCSR04 Sensors
```shell
hcsr04 show
```
* You can show specific pin with specific parameter(name, pin...)
```shell
hcsr04 show name:[WANTED_PIN_NAME]
```

### Measuring Distance of Defined HCSR04 Sensor
``` 
hcsr04 measure [NAME_OF_HCSR04_SENSOR]
```
* Prints the current distance of the given HCSR04 Sensor
### Listening Distance of Defined HCSR04 Sensor
```shell
hcsr04 listen [NAME_OF_hcsr04_SENSOR]
```
* This command will prints the current distance of the given pin every 1 second
* Also, `hcsr04 listen` command accepts some parameters:
```shell
hcsr04 listen [NAME_OF_HCSR04_SENSOR] --[PARAMETER_KEY] [PARAMETER_VALUE]
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
