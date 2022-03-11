# Vim Code Editor for GoozOS
This package allows you to make changes to files while working in the GoozOS operating system terminal.
## Package Install<hr/>
```shell
pkg install vim
```
## Package Using<hr/>
```shell
vim [FILE_PATH]
```
### Save and Exit<hr/>
```shell
:wq!
```
### Only Save<hr/>
```shell
:w!
```
### Only Exit<hr/>
```shell
:q!
```
### Changing Lines<hr/>
```shell
:l [LINE_NUMBER] "[NEW_VALUE]"
```
Ex
```shell
:l 5 "Hello -> World"
```
This operation completely deletes the data in the fifth line and writes the data written in quotes exactly on that line.



