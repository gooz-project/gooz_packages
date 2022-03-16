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
## Creating API
WebGooz is not just a package that provides a server service. At the same time, it also provides the opportunity to write backends with the tools in it.
Written packages must be converted into JSON files in the appropriate format via Gooz CLI. Then it should be thrown into the board containing GoozOS. Afterwards, it should be processed into the server with the Declarative method in WebGooz.
- Example API Sheet for Gooz CLI
```python
def api_register_v2():
    from app.webgooz.main import client
    from app.webgooz.main import breakFlag
    response = "<h1>Register Page</h1>"
    client.send('HTTP/1.0 200 OK\r\nContent-type: text/html\r\n\r\n')
    client.send(response)
    client.close()

def api_hello_v2():
    from app.webgooz.main import client
    from app.webgooz.main import breakFlag
    response = "<h1>Hello v2 Page</h1>"
    client.send('HTTP/1.0 200 OK\r\nContent-type: text/html\r\n\r\n')
    client.send(response)
    client.close()
def api_deneme_register():
    from app.webgooz.main import client
    from app.webgooz.main import breakFlag
    response = "<h1>Deneme Register Page</h1>"
    client.send('HTTP/1.0 200 OK\r\nContent-type: text/html\r\n\r\n')
    client.send(response)
    client.close()

last

```
Each function name represents the endpoint of the API branch. For example, if you have an endpoint named /api/register, your definition should be as follows.
```python
def api_register():
```
