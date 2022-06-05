# LCD Display Package for GoozOS
This package provides use of LCD display
## Package Install
```shell
pkg install lcd
```
## Package Using

### Help
```shell
lcd help
```
* Shows all commands
```shell
lcd help [COMMAND_NAME]
```
* Shows special help for `[COMMAND_NAME]`

### Defining a LCD Display
```shell
lcd var --name [PIN_NAME] --scl [SCL_PIN] --sda [SDA_PIN] --address [I2C_ADDRESS] --size [LCD_SIZE]
```
* `[SCL_PIN]` and `[SDA_PIN]`pin numbers that is used in I2C communicaton protocol must be supported by the board.
* `[I2C_ADDRESS]` is far much important to communicate between device and lcd display. This address can be found on the Internet.
* `[LCD_SIZE]` must be entered as COLUMNxLINE.
* All of these variables must be entered.

### Updating Parameter(s) of a Defined LCD Display
```shell
lcd update [NAME_OF_UPDATING_PIN] --name [NEW_LCD_NAME]
``` 
You can update multiple parameters at the same time
```shell
lcd update [NAME_OF_UPDATING_PIN] --scl [NEW_SCL_PIN] --sda [NEW_SDA_PIN]
```

### Deleting a Defined LCD Display
```shell
lcd delete [NAME_OF_DELETING_LCD]
```
You can also delete all registered LCD display pins
```shell
lcd delete all
```

### Showing Defined LCD Display
```shell
lcd show
```
You can show specific pin with specific parameter(name, scl, sda, address, size)
```shell
lcd show name:[WANTED_PIN_NAME]
```

### Writing Data to Display
```shell
lcd write [NAME_OF_LCD_DISPLAY] --cursor x,y [DATA]
```
* Sets the cursor with --cursor parameter.If not entered, default cursor is set to 0,0.

### Clearing the LCD Display
```shell 
lcd clear [NAME_OF_LCD_DISPLAY]
```

### Turning Off Backlight and Display of the LCD
```shell 
lcd off [NAME_OF_LCD_DISPLAY]
```
