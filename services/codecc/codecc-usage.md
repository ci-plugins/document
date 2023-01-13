# Code check usage

**codecc access procedure:**

1. Configure the code base as the target for code scanning
2. Create pipeline, pull object code
3. Configure the codecc plug-in
4. Execution pipeline
5. View the code review results

## codecc access

### Configuration code base

![img](../../.gitbook/assets/image-20211130150523367.png)

![img](../../.gitbook/assets/image-20211130150820135.png)

**For other types of code bases, see:** [Code Base](../repo.md)

**There are several conditions for associating the gitlab codebase:**

1. Use accesstoken to associate
2. The owner who creates accesstoken must be the maintainer role of the target warehouse
3. accesstoken requires at least api permission
4. The source code address is http/https protocol

The accesstoken is registered using "Credential management". If the accesstoken has been registered in "Credential Management", the corresponding accesstoken can be directly selected when the code base is associated

![img](../../.gitbook/assets/image-20211130152201680.png)

If you register accesstoken in "Credential Management", you can add new credential and jump to the credential management page

![img](../../.gitbook/assets/image-20211130151014566.png)

![img](../../.gitbook/assets/image-20220301101202-KMSOc.png)

For details about how to create gitlab accesstoken, see [Creating an accesstoken](https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html)

Then go back to the Associated code library page, select the accesstoken you just created, and OK

![img](../../.gitbook/assets/image-20220301101202-ZPLrE.png)

**For details about other types of [credentials, see](../ticket.md)**[ Certificate Management](../ticket.md)

### Create pipeline

"Select Project" - "Service" - "Pipeline" - "New Pipeline" - "Project Customization" - "Fill in Pipeline Name" - "New"

![img](../../.gitbook/assets/image-20211130154920245.png)

![img](../../.gitbook/assets/image-20211130165841421.png)

![img](../../.gitbook/assets/image-20211130165902933.png)

![img](../../.gitbook/assets/image-20211130165925767.png)

After the pipeline is created, you need to add the plug-in for code pull and the plug-in for code check. The code check needs to pull the code to the workspace where the construction environment is located, and the pull code needs to select checkout gitlab plug-in

"Add stage" - "Select linux Builder" - "Add Plug-in" - "Select checkout gitlab Plug-in"

![img](../../.gitbook/assets/image-20211130170413760.png)

![img](../../.gitbook/assets/image-20211130170418114.png)

![img](../../.gitbook/assets/image-20211130170455067.png)

![img](../../.gitbook/assets/image-20211130170624022.png)

Configure the checkout gitlab plug-in and select the codebase that you created for the previous step

![img](../../.gitbook/assets/image-20211130171740802.png)

![img](../../.gitbook/assets/image-20211130171852028.png)

### Configuration code check

Add a code review plug-in

![img](../../.gitbook/assets/image-20211130172838584.png)

![img](../../.gitbook/assets/image-20211130172345727.png)

Configure the code check, select the synchronization mode, and select the corresponding engineering language and rule set according to the code base language in "Basic Settings". The rule set is the standard that codecc follows for code scanning. codecc provides the default rule set, and can customize the rule set if the rule set does not meet the requirements. For details about user-defined rule sets, see the following: Select incremental scanning in Scan Configuration for [code check rule](codecc-ruleset.md), and set path whitelist for Path Mask. Once set, code check scans only files in the whitelist path. If the path blacklist is configured, the code checking plug-in does not scan files in the path.

![img](../../.gitbook/assets/image-20211130173035272.png)

![img](../../.gitbook/assets/image-20211201155909271.png)

Path to support wildcards, if it is a complete path, must begin with /, such as the need to block file is' - the name/initial/SRC/main/Java/hello/HelloWorld. Java, Is the path to the white list/initial/SRC/main/Java/hello/HelloWorld. Java.

![img](../../.gitbook/assets/image-20211201155839048.png)

![img](../../.gitbook/assets/image-20211130173112283.png)

![img](../../.gitbook/assets/image-20211130173116075.png)

For details about how to **configure other code check plug-ins**, [see Code Check Configuration](codecc-config.md)

### Execution pipeline

General picture of assembly line:

![img](../../.gitbook/assets/image-20211130195514541.png)

Save and execute pipelining:

![img](../../.gitbook/assets/image-20211130195335957.png)

![img](../../.gitbook/assets/image-20211130195551682.png)

![img](../../.gitbook/assets/image-20211130195617959.png)

### View the code review results

"Wait for execution to finish" - "Click code to check plug-in" - "View Report"

![img](../../.gitbook/assets/image-20211201150104628.png)

![img](../../.gitbook/assets/image-20211201150100160.png)

Click on the number to jump to see the specific problem

![img](../../.gitbook/assets/image-20211201151908164.png)
