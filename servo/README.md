# Servo Motor Package for GoozOS
This package provides using of servo
## Package Install
```shell
pkg install servo
```
## Package Using

### Help
```shell
servo help
```
Shows all commands
```shell
servo help [COMMAND_NAME]
```
Shows special help for command_name


### Defining a Servo
```shell
servo var --name [PIN NAME] --pin [PWM_PIN]
```

### Updating Parameter(s) of a Defined Servo
```shell
servo update [NAME_OF_UPDATING_PIN] --[PARAMETER_NAME] [NEW_PARAMETER]
``` 
* You can update multiple parameters same time: 
```shell
servo update [NAME_OF_UPDATING_PIN] --pin [NEW_PWM_PIN]
```

### Deleting a Defined Servo
```shell
servo delete [NAME_OF_DELETING_SERVO]
```

### Show Defined Servo
```shell
servo show

```

### Actioning the Servo
```shell 
servo degree [PIN NAME] [DEGREE]
```
