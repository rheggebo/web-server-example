# An example, not entirely stable, web server

## Prerequisites
The C++ IDE [juCi++](https://github.com/cppit/jucipp) should be installed.

## Installing dependencies

### Debian based distributions
`sudo apt-get install libboost-thread-dev libboost-regex-dev libboost-date-time-dev`

### Arch Linux based distributions
`sudo pacman -S boost`

### MacOS
`brew install boost`

## Download
```sh
git clone https://github.com/ntnu-tdat3020/web-server-example
```

## Compile and run
### Alternative 1
In a terminal:
```sh
juci web-server-example
```
In juCi++, choose Compile and Run in the Project menu.

### Alternative 2
In a terminal:
```sh
cd web-server-example
mkdir build
cd build
cmake ..
make
./web_server  # Press control-c to stop the server
```

### See web page
#### Alternative 1
Open `http://localhost:8080` in a web browser

#### Alternative 2
In a terminal:
```sh
telnet localhost 8080
GET / HTTP/1.1
                       # Press enter twice here

```

## Debugging
First, stop the web server (if it is running). In juCi++, choosing Kill Last Process in the Project menu.

In a terminal:
```sh
cd build
mkdir debug
cd debug
cmake -DCMAKE_BUILD_TYPE=Debug ../..
make
gdb ./web_server                      # In MacOS, instead use: lldb ./web_server
run
```

#### Backtrace of a stopped process
```sh
bt
```
