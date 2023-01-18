# Pipeline note variable

Pipeline remarks variable: `BK_CI_BUILD_REMARK`, with a short text to distinguish each build content, for example, set 'BK_CI_BUILD_REMARK' to the version number, to indicate the version of the package; Or set platform (windows/pc/ios/Android) to indicate the platform of the package
**Application scenario:**Differentiate pipeline construction history

1. Set the remarks variable
![Set remarks variable](../../../.gitbook/assets/image-variables-set-remark.png)
2. Display note variables
![Set display column](../../../.gitbook/assets/image-variables-config-column.png)
![Select Remarks](../../../.gitbook/assets/image-variables-select-remark.png)
![Display remarks variable](../../../.gitbook/assets/image-variables-remark-view.png)
**Note**: Note variables are displayed only when the pipeline is finished