# How to make my pipeline log display with different colors

In the pipeline logging component, we define the following keywords for plug-in developers to use.

| Key word       | function                                          | remarks                                                      |
| :------------- | :------------------------------------------------ | :----------------------------------------------------------- |
| ##[section]    | The beginning of a Job or plugin                  | If it is the start of a plug-in, it must be included in the Starting of a Job |
| ##[endsection] | The end of a Job or plugin                        | If it is a plug-in ending, it must be included in the Finishing of a Job |
| ##[command]    | Highlight the following string as ShellScripts    | #0070BB                                                      |
| ##[info]       | Mark the following string as the info color       | #48BB31                                                      |
| ##[warning]    | Mark the following string as the color of warning | #BBBB23                                                      |
| ##[error]      | Mark the following string as the error color      | #DE0A1A                                                      |
| ##[debug]      | Mark the following string as the debug color      | #0D8F61                                                      |
| ##[group]      | The beginning of a fold                           |                                                              |
| ##[endgroup]   | The end of a fold                                 |                                                              |

**Take the Bash plug-in as an example:**

```
echo "##[command]whoami"
whoami
echo "##[command]pwd"
pwd
echo "##[command]uptime"
uptime
echo "##[command]python --version"
python --version

echo "##[info] this is a info log"
echo "##[warning] this is a warning log"
echo "##[error] this is a error log"
echo "##[debug] this is a debug log"

echo "##[group] Print SYSTEM ENV"
env
echo "##[endgroup]"
```

You should see something like the image below

![img](../../.gitbook/assets/image2020-1-9_21-59-12.png)
