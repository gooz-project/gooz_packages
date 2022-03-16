# Web Server Package for GoozOS
The WebGooz package allows backend development on devices with GoozOS operating system. People can write their own API arms and implement them on the board easily and quickly with this package.
## How To Install
```shell
pkg install webgooz
```
## How To Use
WebGooz has many different tools. Throughout the article, these will be cited under headings.
### Server Running
Two different types of servers can be raised with WebGooz. The first is attached to the terminal so that no code entry is allowed through the terminal. The other type works in isolation from the terminal and allows terminal inputs.
Although the first option seems illogical, it is a good choice for performance-oriented single-core work where the terminal will not be used.
- Attached Using
```shell
webgooz start --port [PORT]
```
- Deattach Using
```shell
webgooz start -d --port [PORT]
```
### Server Stopping
There are two ways to shut down a server with WebGooz. The first is provided via the URL, while the other is provided via the terminal. In order to use the path provided via terminal, WebGooz must be run with deattach.
- In Terminal
```shell
webgooz close
```
- In API
```
GET or POST -> [IP_ADDRESS]:[PORT]/stop
```
