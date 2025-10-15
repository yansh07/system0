# Hello there!!
  
1. Check your shell - ` echo $ 0 `  
2. Check you OS/distribution - ` cat /etc/os-release `  
3. List all the shells available on your system - ` cat /etc/shells `  

## Note: Before making any sripts - mention this line:  
**#!/bin/[bash/zsh]** or whatever is your shell is - it's not mandatory to write but a good practice to avoid any worst case scenario.  

## File Permission:   
**Before running any script, give your file the "execute" permission so the system can find out, what he have to do with the file, whether read it, write it or execute it like a program/script.**  

``` cd scripts ``` // my directory where script file is located  
``` chmod +x 01_basic.sh ``` //giving execution permission to the file  
``` ./01_basic.sh ``` //script file - in execution mode


## Check your file permissions:  
``` ls -ltr ``` - is used to know the file permissions.  

## Run your scripts using:  
1. ``` ./scripts.sh ```
2. ``` ./path/scripts.sh ```
3. ``` zhs scripts.sh ``` -- you can change or replace 'zsh' with your default shell.  
**And make sure, before running your script, it has 'x'-execute permission.**