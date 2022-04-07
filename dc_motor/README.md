# DC Motor Package for GoozOS
This package provides using of dc_motor
## Package Install
```shell
pkg install dc_motor
```
## Package Using

### Help
```shell
dc_motor help
```
Shows all commands
```shell
dc_motor help [COMMAND_NAME]
```
Shows special help for command_name


### Defining a DC Motor
```shell
dc_motor var --name [PIN NAME] --backward [BACKWARD_PIN] --forward [FORWARD_PIN] --pwm [PWM]
```

### Updating Parameter(s) of a Defined DC Motor
```shell
dc_motor update [NAME_OF_UPDATING_PIN]
``` 
* You can update multiple parameters same time: 
```shell
dc_motor update [NAME_OF_UPDATING_PIN] --name [NEW_DC_MOTOR_NAME] --backward [NEW_BACKWARD_PIN] --forward [NEW_FORWARD_PIN] --pwm [NEW_PWM_PIN]
```

### Deleting a Defined DC Motor
```shell
dc_motor delete [NAME_OF_DELETING_DC_MOTOR]
```

### Show Defined DC Motor
```shell
dc_motor show

```

### Actioning the DC Motor
```shell 
dc_motor write [PIN NAME] --direction [DIRECTION] --speed [SPEED]
```
