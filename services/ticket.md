# Ticket

During pipelination, you may need a variety of credential types to pull up the code base, call the code base API, and access third-party services with an account password.

## Create ticket

![](../.gitbook/assets/image%20%288%29.png)

The following credential types are currently supported:

| 类型 | 描述 |
| :--- | :--- |
| password | Once defined, it is referenced as a pipeline variable in various plug-ins |
| User name + password | Generally, it is used to associate the SVN code base |
| SSH private key | Used when associating with the GitLab codebase (no GitLab event trigger required) |
| SSH private key + private Token | Used when associating with the GitLab codebase (GitLab event trigger required) |
| User name + password+ private Token | Used when associating with the GitLab codebase (GitLab event trigger required) |
| AccessToken | Used when associating with the GitLab codebase (GitLab event trigger required) |

## View ticket

All the associated credentials with permissions can be viewed here.

![](../.gitbook/assets/image%20%2840%29.png)

## Next you may need

* [Create your first pipeline](../tutorials/create-first-pipeline.md)

