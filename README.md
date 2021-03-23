# Terminal Multi-Line Command Editor #
Terminal Multi-Line Input with Edit, Insert, Delete, Print extension for IRIS and Caché   
IRIS and Caché have just single command lines in terminal available   
This Multi-Line Commands Editor also will execute the Multi-line Commands.  
In addtiion, it is independent of access to __%SYS__ and can be installed in any namespace   

It is tested on IRIS/Caché Terminal , Putty, Linux Console, Docker Console,   
Desktop Docker from Windows Command _and WebTerminal._  

This broad range of terminal emulations required navigation without any \<ESC> sequences   
as some of them are quite restrictive on input. So it got a little bit feeling like vi.  
## Installation with Docker ## 
__Prerequisites__   
Make sure you have [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and [Docker desktop](https://www.docker.com/products/docker-desktop) installed.    
__Installation__    
Clone/git pull the repo into any local directory
```
$ git clone https://github.com/intersystems-community/objectscript-docker-template.git
```
Open the terminal in this directory and run:
```
$ set COMPOSE_DOCKER_CLI_BUILD=0
$ docker-compose build
```
Run IRIS container with your project:
```
$ docker-compose up -d
```
__How to Test it in Docker__
Open IRIS terminal:
```
$ docker-compose exec iris iris session iris
USER>ZME
```
## Installation from ZPM ##  
Import ZME.xml to any namespace.  

After the first start you can trigger a system-wide installation in _%SYS_ as %zme     
in combinatin with a Command Extention ZME for simplified use (added to %ZLANGC00.mac)   

At first run and if not a Command Extention just call it from terminal command prompt  
~~~  
  USER>do ^zme  
~~~
## Usage ##
at the prompt _USER:zme>1_   
enter commands as usual in terminal   
trigger execution by an empty line  with \<enter>  

These Editor Commands are implemented:  
~~~
    USER>zme
 
Entering multi line mode.
<enter> => Run multi-line command.
. => Stop multi-line mode
.i, .i<line> => Insert new empty line after <line>
.d, .d<line>, .d<linefrom>:<lineto> => Delete lines
.p, .p<line>, .p<linefrom>:<lineto> => Show lines
.? => show this help
 
.e, .e<line> => Edit line
     ***** line editing commands *****
     .+ => move edit cursor forward
     .- => move edit cursor backward
     .nn => move edit cursor to position nn
     .r => set mode replace at cursor
     .i => set mode insert after cursor
     .d => delete character at cursor
     <enter> => teminate line editing
     <any character> => replace / insert after cursor
     .. => input single .
     ***** line editing commands *****
 
USER:zme>1
~~~
[see Video](https://www.youtube.com/watch?v=vwE-agZxRW8)   
[Article in DC](https://community.intersystems.com/post/terminal-multi-line-command-editor)    
