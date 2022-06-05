# 7 Segment Display Package for GoozOS
This package provides numbers to be written to 7 Segment Display
## Package Install
```shell
pkg install segment7_display
```
## Package Using

### Help
```shell
segment7_display help
```
* Shows all commands
```shell
segment7_display help [COMMAND_NAME]
```
* Shows special help for `[COMMAND_NAME]`

### Defining a 7 Segment Display
```shell
segment7_display var --name [PIN_NAME] --pins a,b,c,d,e,f,g,dt --type [7_SEGMENT_DISPLAY_TYPE]
```
* `--pins` can be any gpio pins of the board. In a 7 segment display, each gpio pins drives a led represented by a letter. These representative letters can be found on the Internet.
* `[7_SEGMENT_DISPLAY_TYPE]` can be anode or cathode.
* a,b,c,d,e,f,g,dt pins must be entered in order.
* All of these variables must be entered.

### Updating Parameter(s) of a Defined 7 Segment Display
```shell
segment7_display update [NAME_OF_UPDATING_PIN] --pins [NEW_PINS]
``` 
You can update multiple parameters at the same time
```shell
segment7_display update [NAME_OF_UPDATING_PIN] --name [NEW_NAME] --type [NEW_TYPE]
```

### Deleting a Defined 7 Segment Display
```shell
segment7_display delete [NAME_OF_DELETING_7SEGMENT_DISPLAY]
```
You can also delete all registered 7 segment display pins
```shell
segment7_display delete all
```

### Showing Defined 7 Segment Display
```shell
segment7_display show
```
You can show specific pin with specific parameter(name, pins, type)
```shell
segment7_display show name:[WANTED_PIN_NAME]
```

### Writing Numbers to 7 Segment Display
```shell 
segment7_display write [PIN_NAME] --number [NUMBER] -dot
```
* `[NUMBER]` can be 0,1,2,3,4,5,6,7,8 or 9.
* If the `-dot` parameter is written, the dot pin value will be HIGH.

### Counting With 7 Segment Display
```shell 
segment7_display count [PIN_NAME] --range [START],[STOP],[STEP] --delay [SLEEP_TIME]
```
* Prints numbers from entered `[START]` to `[STOP]` by increasing or decreasing as much as `[STEP]` to 7 segment display.
* Default `[SLEEP_TIME]`: 1 second

### Turning Off 7 Segment Display
```shell
segment7_display off [PIN_NAME]
```
