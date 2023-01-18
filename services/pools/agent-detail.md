# Build machine details page
After hosting your build machine to bk-ci, you can view the list of build machines and the details of each one on this page.

## builder list
![&#x5728;&#x5217;&#x8868;&#x4E2D;&#xFF0C;&#x53EF;&#x4EE5;&#x67E5;&#x9605;&#x6784;&#x5EFA;&#x673A;&#x7684;&#x57FA;&#x672C;&#x4FE1;&#x606F;&#xFF0C;&#x70B9;&#x51FB;&#x522B;&#x540D;&#x8FDB;&#x5165;&#x6784;&#x5EFA;&#x673A;&#x8BE6;&#x60C5;&#x3002;](../../.gitbook/assets/image%20%2834%29.png)

*** Builder details**
![&#x6784;&#x5EFA;&#x673A;&#x8BE6;&#x60C5;&#x9875;&#x5171;&#x6709; 6 &#x4E2A;&#x529F;&#x80FD;&#x533A;&#xFF0C;&#x5BF9;&#x5E94;&#x529F;&#x80FD;&#x5982;&#x4E0B;&#xFF1A;](../../.gitbook/assets/image%20%2820%29.png)

1. Construct the CPU usage trend chart

2. Create the memory usage trend chart

3. Create the VM network I/O trend chart

4. Create the disk I/O trend chart

5. Copy the installation command: This command is used to reinstall the Agent when the builder reinstalls the system and the Agent directory is deleted

6. Provides 4 important information related to this builder:

   1. Basic information: includes the startup user, installation directory, Agent version, and maximum number of concurrent construction tasks (the default value is 4 to prevent the builder from overloading).
   2. Environment Variables (to be deleted)

   3. Build tasks: All pipeline jobs assigned to this builder will appear here. When you encounter task queuing, you can go here to view specific task assignment information.

   4. Online and offline records of the machine: A record is generated here when the construction machine Agent goes offline.
