# Terminal-Multi-Line-Option
Add Terminal Multi-Line Terminal Option For IRIS and Caché  
IRIS and Caché have just single command lines in terminal available  

This Command extension enables execution of Multi Line Commands from Terminal prompt.

## Installation & Execution ## 
Import %ZML.xml to Namespace %SYS  

Optionally you may add this line to your %ZLANGC00.mac for simplified use:
~~~
ZML do ^%zml quit  ; add multi line command in terminal
~~~

otherwise just call it from terminal command prompt
~~~
  USER>do ^%zml
~~~

## Usage ##
at the prompt _USER:zml:1>_  
enter commands as usual  
trigger execution by an empty line  
stop multi line option with a single '.' (dot) at first position  

## Example ###
~~~
USER>zml
Entering multi line mode. Run with empty line. Stop with single "."
USER:zml:1> for i=1:1:20 {
USER:zml:2> write i
USER:zml:3> write ": "
USER:zml:4> if $x>70 write !
USER:zml:5> }
USER:zml:6> 1: 2: 3: 4: 5: 6: 7: 8: 9: 10: 11: 12: 13: 14: 15: 16: 17:
18: 19: 20:
USER:zml:1> .
USER>
~~~
  with error trapping
~~~
USER>d ^%zml
Entering multi line mode. Run with empty line. Stop with single "."
USER:zml:1> for x=5:-1 {
USER:zml:2>     write ":",x
USER:zml:3>     write ?15,1/x,!  }
USER:zml:4>
:5             .2
:4             .25
:3             .3333333333333333333
:2             .5
:1             1
:0             ^
<DIVIDE>+3
~~~
 routine calls
~~~
USER:zml:1> for i=1,2 {
USER:zml:2>    d ^%SS
USER:zml:3>    write !!,"###########"
USER:zml:4>    hang 2
USER:zml:5> }
USER:zml:6>
             InterSystems IRIS System Status:  1:57 pm 29 Jun 2020
 Process  Device      Namespace      Routine         CPU,Glob  Pr User/Location
   14744                             CONTROL           0,0     8
   14816                             WRTDMN          359,1155  9
   10380                             GARCOL            0,0     8
   14292                             JRNDMN         4600,0     8
   13876                             EXPDMN            0,0     8
    4908  //./nul     %SYS           %SYS.TaskSuper
                                                  116965,8493  8  TASKMGR
   10072  //./nul     %SYS           MONITOR       19301,63    8
   12872  //./nul     %SYS           CLNDMN          692,65    8
    8308  //./nul     %SYS           RECEIVE       15801,839   8
    5512  //./nul     %SYS           ECPWork           0,0     8  ECPWORK
    2692  |TCP|51773  %SYS           %SYS.SERVER       0,0     8
   14884  //./nul     %SYS           LMFMON        21985,629   8
    2808  |TCP|CEMPER9:51773
                      USER           %SYS.BINDSRV2146884,2282268  _SYSTEM
    2516  //./nul     %SYS           SYS.VSSWriter     0,0     8  VSS Writer
   14416  //./nul     %SYS           %SYS.Monitor.Control
                                                 2047945,76423 8
   14940  |TCP|localhost:51773
                      %SYS           %SYS.cspServer3
                                                  138785,16984 8  UnknownUser
 
Press Q or q to quit, any other character to continue. q
 
 
###########
USER:zml:1>
~~~
