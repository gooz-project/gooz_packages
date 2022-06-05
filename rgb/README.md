# RGB Led Package for GoozOS
This package provides light in different colors with anode RGB and cathode RGB
## Package Install
```shell
pkg install rgb
```
## Package Using

### Help
```shell
rgb help
```
* Shows all commands
```shell
rgb help [COMMAND_NAME]
```
* Shows special help for `[COMMAND_NAME]`

### Defining a RGB Led
```shell
rgb var --name [RGB_LED_NAME] --red [RGB_RED_PIN] --green [RGB_GREEN_PIN] --blue [RGB_BLUE_PIN] --type [RGB_TYPE]
```
* `[RGB_RED_PIN]`,`[RGB_GREEN_PIN]` and `[RGB_BLUE_PIN]` can be any pwm pins of the board.
* `[RGB_TYPE]` must be anode or cathode.
* All of these variables must be entered.

### Updating Parameter(s) of a Defined RGB Led
```shell
rgb update [NAME_OF_UPDATING_PIN] --pin [NEW_RGB_LED_PIN]
``` 
You can update multiple parameters at the same time 
```shell
rgb update [NAME_OF_UPDATING_PIN] --name [NEW_RGB_LED_NAME] --type [NEW_RGB_LED_TYPE]
```

### Deleting a Defined RGB Led
```shell
rgb delete [NAME_OF_DELETING_RGB_LED]
```
You can also delete all registered rgb led pins
```shell
rgb delete all
```

### Showing Defined RGB Led
```shell
rgb show
```
You can show specific pin with specific parameter(name, red, green, blue, type)
```shell
rgb show name:[WANTED_PIN_NAME]
```

### Turning the Light On In Different Colors
```shell 
rgb write [NAME_OF_RGB_LED] --color [COLOR]
```
* `[COLOR]` can be red, blue, green, white, yellow, orange, pink, purple or cyan.

### Turning the Light Off
```shell 
rgb off [NAME_OF_RGB_LED]
```
