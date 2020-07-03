# Terminal Multi-Line Command Editor #
Terminal Multi-Line Input with Edit, Insert, Delete, Print extension for IRIS and Caché 
IRIS and Caché have just single command lines in terminal available  
This Multi-Line Commands Editor also wil-l execute the Commands.  
In addtion it is now independent of access to __%SYS__ an can be installed in any namespace 

Is is tetsted on IRIS / Caché Terminal , Putty, Linux Console, Docker Console,
Desktop Dockker wieht Windows Command and WebTerminal.

This broad range of termnal emulatins required navigation without any <ESC> sequences as
some of them are quite restrictive on input. So it got a litlebi vi feeling.
  
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
at the prompt _USER:zme>1_  
enter commands as usual interminal 
trigger execution by an empty line  

These Editor Commands are implemented:

USER>d ^zme
 
~~~
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

    USER:zml>1
~~~
