# Associated code base

## Q1: Common causes of error associated with GitLab code base

![img](../../../.gitbook/assets/repo_gitlab.png)

1. Use Personal Access Tokens instead of project tokens.

2. Make sure that Access_Tokens are given permissions when they are generated. The corresponding API permissions must be included.

3. If it is self-built GitLab, please confirm whether API of "repository/branches" is available.

https://docs.gitlab.com/ee/api/branches.html

4. If GitLab is accessed using https. Check whether http - >https is performed in the code base. BKCI defaults to http for code base access.

If no skip is performed, please click this temporary solution to modify the BKCI file:

```
vim /data/bkce/etc/ci/application-repository.yml

#修改application-repository.yml文件，把apiUrl 修改为 https
#gitlab v4.
gitlab:
apiUrl: https://devops.bktencent.com/api/v4
```

Restart bk-ci-repository.service

```
systemctl restart bk-ci-repository.service
```

## Q2: Failed to associate the GitHub codebase

There are still some issues with BKCI's connection to GItHub. If you must use the GitHub codebase, follow this method. [How do I associate the GitHub codebase](https://bk.tencent.com/s-mart/community/question/3184?type=article)