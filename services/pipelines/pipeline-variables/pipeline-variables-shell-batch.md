# Use variables in the Shell/Batchscript plugin
## Use variables in Shell plug-ins
```shell
# References the global variable WORKSPACEcd ${WORKSPACE}

Set custom variables: setEnv 'variable name' 'variable value'
setEnv 'version' '3.2.16'
```

setEnv is the output parameter of the current shell, which takes effect only in the downstream. It cannot be printed in the current shell.
```shell
# References version in subsequent shell plugins
echo ${version}
```

## Use variables in the Batchscript plugin
```bat
REM refers to the global variable WORKSPACE
cd %WORKSPACE%

REM You can set the parameters passed between plugins using the setEnv function
REM call:setEnv "FILENAME" "package.zip" 
REM then references this variable in subsequent plugin forms using %FILENAME%

call:setEnv "FILENAME" "package.zip"

```

Reference FILENAME in a subsequent Batchscript plug-in```bat


```
echo on
echo %FILENAME%
