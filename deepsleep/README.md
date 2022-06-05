# DEEPSLEEP Package for GoozOS
This package provides deepsleep feature for GoozOS
## Package Install
```shell
pkg install deepsleep
```
## Package Using

### Help
```shell
deepsleep help
```
* Shows all commands
```shell
deepsleep help [COMMAND_NAME]
```
* Shows special help for [COMMAND_NAME]

### Going Directly to Deepsleep
```shell
deepsleep
```
* The machine goes into an eternal sleep until you wake it up manually(onboard reset button).

### Defining for the Deepsleep Features
```shell
deepsleep var --name [PIN_NAME] --pin0 [PIN_NUMBER] --pin1 [BACKUP_PIN_NUMBER1] --pin2 [BACKUP_PIN_NUMBER2]
```
* All of these variables must be entered.
* Registration must be required to use the machine externally(gpio/button) or with touchpad.
* --pin0 parameter must be entered, --pin1 and --pin2 parameters are optional.
* All pins entered are set for external button or touchpad.

### Updating Parameter(s) of a Defined Deepsleep Pin
```shell
deepsleep update [NAME_OF_UPDATING_PIN] --pin0 [NEW_PIN_NUMBER]
``` 
You can update multiple parameters at the same time
```shell
deepsleep update [NAME_OF_UPDATING_PIN] --name [NEW_DEEPSLEEP_PIN_NAME] --pin1 [NEW_BACKUP_PIN_NUMBER]
```

### Deleting a Defined Deepsleep Pin
```shell
deepsleep delete [NAME_OF_DELETING_PIN]
```
You can also delete all registered deepsleep pins
```shell
deepsleep delete all
```

### Showing Defined Deepsleep Pin
```shell
deepsleep show
```
You can also show specific pin with specific parameter(name, pin0, pin1, pin2)
```shell
deepsleep show name:[WANTED_PIN_NAME]
```

### Waking the Machine Up From Deepsleep
```shell 
deepsleep wake [PIN_NAME]/[TIME] -[WAKE_REASON]
```
* -[WAKE_REASON] can be -external_button, -touchpad or -timer
* The registered pin named [PIN_NAME] must be entered if the machine is wanted to be woken up externally(gpio/button) or with touchpad.
* the amount of [TIME] the machine will sleep must be entered if the machine is wanted to be woken up with timer.
