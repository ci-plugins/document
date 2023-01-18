# Publish a CI image
## Prepare the container image
If no image is available, see [build and Host a CI Image](image-build.md)
## Publish container image
### Entrance
Worktable -&gt; Container mirror image -&gt; Associated mirror
![](../../.gitbook/assets/image%20%2839%29.png)

### Associated mirror
![](../../.gitbook/assets/image%20%281%29.png)

1. The unique identity of the image in the R&D store, not the same name
2. During image publishing, check whether the image function is normal under this debugging item. It is recommended to use dedicated test items for verification
3. If the image is a private image, create a credential in Credentials management and associate it with the image. At execution time, the system uses this credent to pull the image

### Mount/upgrade image
**Entry is as follows**
![](../../.gitbook/assets/image%20%2846%29.png)

**Fill in the basic information**
![](../../.gitbook/assets/image%20%2831%29.png)

![](../../.gitbook/assets/image%20%2819%29.png)

1. Mirror the library host
   * If docker hub image is used, you can leave this field blank or enter docker.io

2. Image name, including the image namespace

3. Image tag

4. Credentials: Private mirrors need to specify access credentials

5. Dockerfile: It will be displayed in the R&D store for users to understand the details of the image
    When upgrading an image, there are three upgrade modes:
    ![](../../.gitbook/assets/image%20%2841%29.png)

1. Incompatible upgrade:
   * Used when the mirror function logic has changed significantly and is incompatible with older versions
   * After this version is released, the pipeline that uses the image does not automatically upgrade the version. You need to manually change the version number
   * Major version number +1
2. Compatible function update:
   * Used when the mirror function is updated or added \(does not affect existing users \)
   * After this type of version is released, pipelinesthat are already using the image and version number is \[major version.latest] will automatically use the new version without manually editing the pipelines5
   * Minor version number +1
3. Compatible problem correction:

   * Mirror function compatible with older versions, only to do problem correction

   * After this type of version is released, pipelinesthat are already using the image and version number is \[major version.latest] will automatically use the new version without manually editing the pipelines5

   * Correction sign +1


**Verify image**
After the release is submitted, you can verify that the mirroring function meets expectations under the debugging project
     ![](../../.gitbook/assets/image%20%2814%29.png)

1. Test: Click and jump to the pipeline service of the debugging project. You can use this image to perform the pipeline Job and verify whether the function meets expectations
2. If any problem is found, push the image again, verify and test it again
   * Image verification steps, only verify whether the image can be successfully pulled, whether the function is normal needs to be tested by the publisher
3. After the test is OK, continue the release process manually and release the image to the R&D store for other users/projects
