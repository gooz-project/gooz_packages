# Goell Package
The Goell package aims to make system configurations of boards containing GoozOS easy and to perform CI/CD tasks effectively.
## Package Install<hr/>
```shell
pkg install goell
```
## How To Use<hr/>
The package is very easy to use. To configure, you need to define a JSON file in the package. For example, you have a configuration file named sysconf.json. In this case, what you need to do is to run the code below.
```shell
goell sysconf.json
```
## Configuration Methods<hr/>
The system consists of sections and packages. The purpose of the sections is to perform CI/CD tasks more easily and to provide a synchronous operation.<br/>
Sections are sent to you as a message during use. Bundles are often used in bulk transactions over a single product. For example, if you have 3 commands related to wifi and you want to define it as a "Wifi Init" section, you can use "package":"wifi".<br/>
For mixed operations, you can use "goozshell".
### Example Configuration File
```json
{
    "configuration":[
        {
            "section":"Wifi Section",
            "package":"wifi",
            "commands":[
                "on",
                "ls",
                "connect --name [SSID] --password [WIFI_PASSWORD]"
            ]
        },
        {
            "section":"Pin Section",
            "package":"pin",
            "commands":[
                "gpio show",
                "pwm show"
            ]
        },
        {
            "section":"Gooz Shell",
            "package":"goozshell",
            "commands":[
                "pin gpio write newPin HIGH",
                "delay 2",
                "pin gpio write newPin LOW"
            ]
        }
    ]
}
```
