# LDR Sensor Package for GoozOS
This package provides light intensity measurement with LDR Sensor
## Package Install
```shell
pkg install ldr
```
## Package Using

### Help
```shell
ldr help
```
* Shows all commands
```shell
ldr help [COMMAND_NAME]
```
* Shows special help for `[COMMAND_NAME]`

### Defining a LDR Sensor
```shell
ldr var --name [LDR_SENSOR_NAME] --pin [ADC_PIN]
```
* `[ADC_PIN]` can be any adc pin of the board.
* All of these variables must be entered.

### Updating Parameter(s) of a Defined LDR Sensor
```shell
ldr update [NAME_OF_UPDATING_PIN] --pin [NEW_LDR_SENSOR_PIN]
``` 
You can update multiple parameters at the same time
```shell
ldr update [NAME_OF_UPDATING_PIN] --name [NEW_LDR_SENSOR_NAME] --pin [NEW_LDR_SENSOR_PIN]
```

### Deleting a Defined LDR Sensor
```shell
ldr delete [NAME_OF_DELETING_LDR_SENSOR]
```
You can also delete all registered ldr sensor pins
```shell
ldr delete all
```

### Showing Defined LDR Sensor
```shell
ldr show
```
You can show specific pin with specific parameter(name, pin)
```shell
ldr show name:[WANTED_PIN_NAME]
```

### Printing the Value of Light Intensity Measured by LDR Sensor
```shell 
ldr read [PIN_NAME] --max [MAX_NUMBER] --min [MIN_NUMBER]
```
* Default value range is min:0 to max:4095.
* --max and --min parameters set the value range according to the entered `[MAX_NUMBER]` and `[MIN_NUMBER]`.

### Listening Light Intensity Values Measured by LDR Sensor
```shell 
ldr listen [PIN_NAME] --delay [SLEEP_TIME] --file [FILE_NAME] --max [MAX_NUMBER] --min [MIN_NUMBER] --loop [MEASURING_LOOP]
```
* If `[MEASURING_LOOP]` is not entered, loop lasts until "thread stop `[THREAD_ID]`" command.
* `[THREAD_ID]` is seen with "thread show" command.
* If `[FILE_NAME]` is not entered, values will not be saved.
* Default `[SLEEP_TIME]`: 1 second.
