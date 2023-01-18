# Code check FAQ

**Q: How do I configure the scan directory after codecc plug-in is added to the pipeline?**

Space occupied, to be filled

**Q: Code analysis error: Detected that this is a third party build machine**

![img](../../.gitbook/assets/企业微信截图_16393674859420.png)

Third-party build machines are not supported for code analysis. You can use a public build machine to execute the plug-in

**Q: Some code analysis tasks are no longer needed. How do I delete them**

![img](../../.gitbook/assets/企业微信截图_16394863726885.png)

It does not provide the deletion function. You can disable it if you do not need to

![img](../../.gitbook/assets/wecom-temp-86ae0a86fe2fc72292be8a99ea3aca3c.png)img

**Q: How does codecc path masking work**

Space occupied, **to be filled**

**Q: Some classes of std::string, we want it to be a const static variable, but the current code inspection says no, it must be const char\*. This rule is not quite understood, how to find the principle behind the rule?**

![img](../../.gitbook/assets/image-20220301101202-dqwHG.png)

Codecc cpplint rule is based on the Google c + + code of the specification, you can refer to https://google.github.io/styleguide/cppguide.html#Names_and_Order_of_Includes, The problem here is that fstream, as a c++ system header file, should be included before third-party introductions such as boost/*

**Q: Does codecc detect lua code in the default language?**

lua code checking is not supported yet

**Q: I can't see the source code for the code check. It shows that the code snippet cannot be obtained. Please make sure that. I can't see the source code for the code check. It shows that the code snippet cannot be obtained. Please make sure that you have permission on the code base and that the file is not deleted from the code base**

![img](../../.gitbook/assets/企业微信截图_162764646337.png)

1. Verify that you have "view" and "use" permissions for the code base
2. Use the "Checkout gitlab" plug-in to pull the code

![img](../../.gitbook/assets/wecom-temp-cf8119964a088f29ea8c6ab91207001b.png)

**Q: Can the rules of codecc be customized or modified, for example, if you want to add some naming checks on your side**

codecc's rules do not support customization at the moment, and only a few rules can modify parameters

![img](../../.gitbook/assets/wecom-temp-08d0c28a28b7da8ca0aa399a96834f15.png)img

![img](../../.gitbook/assets/wecom-temp-54ddc1c54d449c261c04721f0cf403d2.png)

**Q: Code check fails when the incremental scan is configured on the new public build machine**

![img](../../.gitbook/assets/企业微信截图_16388456801202.png)img

When switching the builder, a full scan should be carried out first, and the fresh checkout mode should be selected by gitlab checkout
