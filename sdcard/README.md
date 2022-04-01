# SD Card Package for GoozOS
This package provides connect SD card to GoozOs with microSD adapter.
## Package Install
```shell
pkg install sdcard
```
## Package Using

### Help
```shell
sdcard help
```

### Defining a SD Card
```shell
sdcard register --name [SDCARD_NAME] --miso [MISO_PIN] --mosi [MOSI_PIN] --sck [SCK_PIN] --cs [CS_PIN]
```

* All of these variables must be entered.
### Updating Parameter(s) of a Defined SD Card
```shell
sdcard update [NAME_OF_UPDATING_PIN] --miso [NEW_MISO_PIN]
``` 

* You can update multiple parameters same time: 
```shell
sdcard update [NAME_OF_UPDATING_SDCARD] --miso [NEW_MISO_PIN] --sck [NEW_SCK_PIN]
```

### Deleting a Defined SD Card
```shell
sdcard delete [NAME_OF_DELETING_SDCARD]
```

### Show Defined SD Cards
```shell
sdcard show
```
* It shows all saved sdcard pins
* Or you can show specific pins with following way:
```shell
sdcard show sck:15
````
* It shows just pins which [SCK_PIN] = 15

### Mounting An SD Card
``` 
sdcard mount [SDCARD_NAME]
```
* After this command, the new folder named ``SDCARD_NAME`` must have been added to the main folder.
* Now you can use this folder just like any system folder
  * -> cd ``SDCARD_NAME``
  * -> ls
```
sdcard mount [SDCARD_NAME] as [FOLDER_NAME]
```
* If you use mount command with as, you can choose a ```FOLDER_NAME`` which different from ``SDCARD_NAME``
* The added folders name will be ``[FOLDER_NAME]``
### Umounting an SD Card
```
sdcard umount [FOLDER_NAME]
```
* You must use the ``FOLDER_NAME`` 
* Ff you used mount command without `as`, it already same as ``SDCARD_NAME``
