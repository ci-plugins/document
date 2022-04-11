# 在Shell/Batchscript插件里使用变量

## 在Shell插件里使用变量

```shell
# 引用全局变量WORKSPACE
cd ${WORKSPACE}

# 设置自定义变量: setEnv '变量名' '变量值'
setEnv 'version' '3.2.16'
```

setEnv 设置的是当前shell的输出参数，在下游才会生效，当前的shell里打印不出来的。

## 在Batchscript插件里使用变量

```bat
REM 引用全局变量WORKSPACE
cd %WORKSPACE%

REM 您可以通过setEnv函数设置插件间传递的参数 
REM call:setEnv "FILENAME" "package.zip" 
REM 然后在后续的插件的表单中使用%FILENAME%引用这个变量
call:setEnv "FILENAME" "package.zip"

```
