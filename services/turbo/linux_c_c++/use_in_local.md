---
description: The following tutorial will guide you through how to use the acceleration solution in the native build machine after you have successfully customized it
---

# Use acceleration on private build machines
## Step1 **First install the Accelerator kit on the machine (do this using root)**
```text
/ bin/bash - c "$(curl http://<your service domain name> /turbo-client/disttask/install. Sh)"
```

## Step2 Copy the acceleration scheme ID

You can get the ID on the View scheme page:
![](../../../.gitbook/assets/image%20%2862%29.png)

## Step3 Use the acceleration tool to start acceleration

For example, the original compiled script is:

```text
make -j gamesvr
```

Use the tool installed in Step 1, combined with the scenario ID in Step 2, to perform the acceleration:
```text
bk-boosters bt cc-p <ID copied in step 2> --hook -a "make -j@BK_JOBS gamesvr"
```

The bk-booster is the accelerator provided by the plug-in to start the acceleration.
Parameter meanings in the command are
* -bt cc: cc is used for c/ C ++ compilation on linux.
* -p &lt; Acceleration program ID&gt; , specify the scheme ID.
* --hook, open the hook command, will automatically hijack gcc/clang and other compilers to achieve acceleration.
* -a "make -j@BK\_JOBS gamesvr", specifying the compile command to execute, with @BK\_JOBS as a placeholder, automatically replaced at run time with the recommended amount of concurrency.
