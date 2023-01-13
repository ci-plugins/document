---
description: To use a compile acceleration service, you first need to customize an acceleration scheme.
---

# Customize Linux C/C++ acceleration scheme

## Step1 Go to BKCI and navigate to Services → Compile Acceleration
For the first time, the following page is displayed. Click "Use now" to enter the solution customization page:
![](../../../.gitbook/assets/image%20%2863%29.png)

Enter the scheme list management when the scheme is available:
![](../../../.gitbook/assets/image%20%2838%29.png)

## Step2 Enter the solution configuration
![](../../../.gitbook/assets/image%20%2864%29.png)

Solution configuration includes:
1. Scheme name: As the identification name, you can fill in such as "xxx personal acceleration", "Daily Build Acceleration", "Builder Package Acceleration" and so on.
2. Acceleration mode: Select the acceleration mode to be created. Once created, the acceleration mode **cannot be modified **
3. Scheme description: You can write some remarks or instructions here.
4. Compilation environment: Select the corresponding compilation environment according to your local environment. If there is no compilation environment in the list, please contact the administrator **quick support **.
5. Enable ccache: Select whether to enable ccache as required. If this option is enabled, the system prioritises ccache locally.
6. Priority scheduling region: Select the nearest scheduling region based on the local environment.
## Step3 Submit registration and obtain the exclusive scheme ID
After clicking Submit, a unique scheme ID will be generated. This ID can also be queried in the "Accelerated Scheme" → click the scheme name to enter the details page.
The scheme ID is an accelerated credential that contains your environment information, configuration information, and permission information. **Please keep your scheme ID safe and do not disclose it to others. **
![](../../../.gitbook/assets/image%20%2865%29.png)



