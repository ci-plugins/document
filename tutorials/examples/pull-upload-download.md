# Code pull + product library upload download
* Click on the Code base, (for details about the code base, see the Code Base directory)
![](../../.gitbook/assets/image-20211212214606792.png)

* Select associated Gitlab codebase
![](../../.gitbook/assets/image-20211205163725597.png)

* Click "Add", it will automatically jump to credential management -- add new credentials, obtain the AccessToken on gitlab to fill in, click "OK";
![](../../.gitbook/assets/image-20211205164052362.png)

* Go back to the code base, access credentials select Credentials [demo], OK
![](../../.gitbook/assets/image-20211205164627965.png)

* Create pipelining
![](../../.gitbook/assets/image-20211213100550657.png)

Add a new stage
![](../../.gitbook/assets/image-20211213100650213.png)

Add checkout gitlab plug-in, associate the created code base, and pull by branch
![](../../.gitbook/assets/image-20211205170423284.png)

Package the code by adding shell plug-ins, viewing the current workspace, and pulling down the code directory
![](../../.gitbook/assets/image-20211209202103728.png)

Save the shortur.zip file from your current workspace to the artifact library using the upload artifacts plugin
Note: When multiple types of builder are used (public builder + private builder or multiple different private builders) and the build products need to be used between different builders (not limited to the pulled code), you can upload files/folders to the artifact library and download the corresponding files in the artifact library from the Job where the file is to be used
* Add the upload artifacts plugin
![](../../.gitbook/assets/image-20211209202425994.png)

* download artifacts plugin -- Download files from the artifacts library into the workspace under the current Job
Add a new stage
![](../../.gitbook/assets/image-20211209202505648.png)

Add the Download artifacts plug-in, which automatically finds the source path of the artifact library based on the content filled in, and then downloads it to the current workspace
![](../../.gitbook/assets/image-20211209203143751.png)