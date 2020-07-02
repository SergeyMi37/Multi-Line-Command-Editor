# Terminal-Multi-Line-Extended
Terminal Multi-Line Input with Edit, Insert, Delete, Print extension for IRIS and Caché 
IRIS and Caché have just single command lines in terminal available  
This extended Multi Line Commands includes a set of editing features which required a 90% rewrite of the predecessor.  
In addtion it is now independent of access to __%SYS__ an can be installed in any namespace 

## Installation & Execution ## 
Import ZME.xml to any namespace.

For a system wide installation in  %SYS just renae it from zme to %zme  
You may add this line to your %ZLANGC00.mac for simplified use:
~~~
ZME do ^%zme quit  ; add multi line command extended in terminal
~~~

otherwise just call it from terminal command prompt
~~~
  USER>do ^zme
~~~

## Usage ##
at the prompt _USER:zml:1>_  
enter commands as usual  
trigger execution by an empty line  
stop multi line option with a single '.' (dot) at first position  

## Example ###
~~~

USER>
~~~
  with error trapping
~~~
USER>

~~~
