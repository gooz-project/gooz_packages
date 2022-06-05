# MPU6050 Sensor Package for GoozOS
This package provides gyro, acceleration and temperature measurement with MPU6050 Sensor
## Package Install
```shell
pkg install mpu6050
```
## Package Using

### Help
```shell
mpu6050 help
```
* Shows all commands
```shell
mpu6050 help [COMMAND_NAME]
```
* Shows special help for `[COMMAND_NAME]`


### Defining a MPU6050 Sensor
```shell
mpu6050 var --name [PIN_NAME] --scl [SCL_PIN] --sda [SDA_PIN]
```
* `[SCL_PIN]` and `[SDA_PIN]` pin numbers that is used in I2C communicaton protocol must be supported by the board.
* All of these variables must be entered.

### Updating Parameter(s) of a Defined MPU6050 Sensor
```shell
mpu6050 update [NAME_OF_UPDATING_PIN] --scl [NEW_MPU6050_SCL_PIN]
``` 
You can update multiple parameters at the same time 
```shell
mpu6050 update [NAME_OF_UPDATING_PIN] --name [NEW_MPU6050_SENSOR_NAME] --sda [NEW_MPU6050_SDA_PIN]
```

### Deleting Defined MPU6050 Sensor
```shell
mpu6050 delete [NAME_OF_DELETING_MPU6050_SENSOR]
```
You can also delete all registered mpu6050 sensor pins
```shell
mpu6050 delete all
```

### Showing Defined MPU6050 Sensor
```shell
mpu6050 show
```
You can show specific pin with specific parameter(name, scl, sda)
```shell
mpu6050 show name:[WANTED_PIN_NAME]
```

### Printing the Value of Gyro, Acceleration and Temperature Measured by MPU6050 Sensor
```shell 
mpu6050 read [PIN_NAME] --gyro x,y,z --acceleration x,y,z --temperature [STATUS]
```
* If temperature is desired to be measured `[STATUS]` should be "on", otherwise --temperature does not need to be entered.
* Only the parameters that are desirable to be measured should be entered.For example, if the x direction of gyro is desired to be measured,"--gyro x" is enough.

### Listening Gyro, Acceleration and Temperature Values Measured by MPU6050 Sensor
```shell 
mpu6050 listen [PIN_NAME] --gyro x,y,z --acceleration x,y,z --temperature [STATUS] --loop [MEASURING_LOOP] --delay [SLEEP_TIME] --file [FILE_NAME]
```
* If temperature is desired to be measured `[STATUS]` should be "on".
* Only the parameters that are desirable to be measured should be entered.
* If `[MEASURING_LOOP]` is not entered, loop lasts until "thread stop `[THREAD_ID]`" command
* `[THREAD_ID]` is seen with "thread show" command
* Default `[SLEEP_TIME]`: 1 second
* If `[FILE_NAME]` is not entered, values will not be saved
