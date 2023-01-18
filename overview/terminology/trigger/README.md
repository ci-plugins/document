# Trigger

bk-ci supports a variety of ways to trigger the pipeline:
* API trigger

* Code base event firing

* Child pipeline call plug-in trigger

* timed trigger

* Manual trigger

* Remote trigger
  The built-in BK\_CI\_START\_TYPE value also varies depending on the trigger mode. You can use this value in the pipeline's subsequent plugins as needed:

  | 触发方式               | BK\_CI\_START\_TYPE 值 |
  | :--------------------- | :--------------------- |
  | Remote Trigger         | REMOTE                 |
  | Manual Trigger         | MANUAL                 |
  | Timing Trigger         | TIME\_TRIGGER          |
  | Child-Pipeline Trigger | PIPELINE               |
  | Code Base Hook Trigger | WEB\_HOOK              |
  | API Trigger            | SERVICE                |

  ![](../../../.gitbook/assets/image%20%2845%29.png)

