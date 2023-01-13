# Code check rule set

## User-defined rule sets

If the number of rules in the default rule set is small and does not meet user requirements, or some rules in the rule set do not meet the code style of the enterprise or developers, you can create a custom rule set

> Scenario simulation: The "build/include_what_you_use" rule in the CodeCC default (C++) default rule set does not conform to the code development style of our organization and would like to remove it

### Create rule set

A user-defined rule set is related to a project. Before creating a user-defined rule set, select a target project

![img](../../.gitbook/assets/image-20210826175151943.png)

By selecting the CodeCC default (C++) as "based", the custom rule set can be added or deleted from this default rule set

![img](../../.gitbook/assets/image-20210826175625206.png)

### Add-delete rule

A custom rule set based on the CodeCC default (C++) will contain all rule entries of the CodeCC default (C++) by default. Users can locate the unnecessary rule "build/include_what_you_use" and uncheck it to save the rule set

![img](../../.gitbook/assets/image-20210826175951021.png)

### Pipelined re-selects the custom rule set

Cancel the default rule set in the pipeline, select Custom rule set, and save the pipeline again

![img](../../.gitbook/assets/image-20210826180347933.png)