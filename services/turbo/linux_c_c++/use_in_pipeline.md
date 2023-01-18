---
description: The following tutorial will guide you through how to use the acceleration solution in the pipeline after you have successfully customized it
---

# Compile acceleration in pipelining
## Preparation work
If your pipeline is on a private build machine, install client as root on your machine in advance.
```text
/ bin/bash - c "$(curl http://<your service domain name> /turbo-client/disttask/install.sh)"
```

If your pipeline uses a public builder, this step is **unnecessary**.
## Step1 Modify the compilation script
Suppose the original compiled script is:
```text
cd ${WORKSPACE}/master

./autogen.sh
./configure --disable-pump-mode

make clean
make -j all
```

As you can see, the commands in the previous section are doing some preparatory work. The actual compiling instructions are:
```text
make -j all
```

We just need to modify this sentence to execute the compile instruction with the accelerator and get the acceleration.
```text
bk-booster -bt cc -p $TURBO_PLAN_ID --hook -a "make -j@BK_JOBS all"
```

The bk-booster is the accelerator provided by the plug-in to start the acceleration
Parameter meanings in the command are
* -bt cc: cc is used for c/ C ++ compilation on linux.
* -p $TURBO\_PLAN\_ID: specifies the scheme ID. In the Turbo Compilation Acceleration plug-in, the ID of the selected scheme is injected by default.
* --hook, open the hook command, will automatically hijack gcc/clang and other compilers to achieve acceleration.
* -a "make -j@BK\_JOBS all", specifying the compile command to execute, with @BK\_JOBS as a placeholder that will be automatically replaced with the recommended amount of concurrency at run time.
## Step2 Open the pipeline and add the plugin "**Turbo Compilation Acceleration**"
![](../../../.gitbook/assets/image%20%2867%29.png)

Note: This step requires the addition of a code plug-in
## Step3 Select a registered acceleration scheme
![](../../../.gitbook/assets/image%20%2860%29.png)

## Step4 Configure the compilation script

Compiled scripts can be submitted to the code base using file management, and the pipeline only needs to fill in the relative path of the script file:
![](../../../.gitbook/assets/image%20%2861%29.png)

You can also configure compilation scripts into plug-ins:
![](../../../.gitbook/assets/image%20%2856%29.png)



