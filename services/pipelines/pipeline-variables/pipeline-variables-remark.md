# 使用备注变量

流水线备注变量：`BK_CI_BUILD_REMARK`，用简短的文字说明来区分每次构建的内容，比如将`BK_CI_BUILD_REMARK`设置成版本号，用来表示该次打包产物的版本；又或者设置成平台（windows/pc/ios/andriod）表示本次打包的平台

**适用场景：** 区分流水线的构建历史

1.  设置备注变量

    <img src="../../../.gitbook/assets/image-variables-set-remark.png" alt="设置备注变量" data-size="original">
2.  展示备注变量

    <img src="../../../.gitbook/assets/image-variables-config-column.png" alt="设置显示列" data-size="original">

    <img src="../../../.gitbook/assets/image-variables-select-remark.png" alt="选择备注" data-size="original">

    <img src="../../../.gitbook/assets/image-variables-remark-view.png" alt="展示备注变量" data-size="original">

**注意**：备注变量只有当流水线执行结束才会展示
