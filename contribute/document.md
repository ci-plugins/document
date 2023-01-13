# Contributing to bkci document

In the process of writing, it is inevitable that there will be some imperfections. We hope that you can help us to continuously improve the quality of the document and help more people.
## method
Submit an Issue or Pull Request on GitHub at https://github.com/ci-plugins/document
## Document specification
1. The document is written in markdown syntax
2. Pictures shall be placed `.gitbook/assets` and the name of the picture shall not be the same as that of the existing picture
3. Only upper and lower case letters, numbers, `-`, and `_` are allowed in the picture name
4. The co-creator can launch PR for the master branch, and the administrator will review the PR
Document co-construction process
### 1. Fork repository

To get started, log in, visit https://github.com/ci-plugins/document, and fork to your github account
![image-contributing-fork-repo](../.gitbook/assets/image-contributing-fork-repo.png)

![image-contributing-fork-success](../.gitbook/assets/image-contributing-fork-success.png)

### 2. Clone  

Before cloning the repository, ensure that the repository you fork out is consistent with the source repository. If you are behind the source repository, consider 'Fetch Upstream' first, as shown in Step 4
`git clone https://github.com/xxxx/document`

### 3. Change & Commit

```
cd /path/to/document
git config user.name "${your github username}"
git config user.mail "${your email}"
echo "add xxx" > xxx.md # simulates the operation of editing a documentgit commit -m "add xxx"
```

### 4. Fetch upstream

Before committing to your repository, check to see if the code you fork out is behind the source repository. If it is, start with 'Fetch upstream' to synchronize the updates from the source repository to your repository. 'compare' looks at code differences, 'Fetch and merge' merges source repository code into its own repository
![image-contributing-fetch-upstream](../.gitbook/assets/image-contributing-fetch-upstream.png)

![image-contributing-fetch-merge](../.gitbook/assets/image-contributing-fetch-merge.png)

![image-contributing-merge-upstream-success](../.gitbook/assets/image-contributing-merge-upstream-success.png)


### 5. Git pull

In addition to synchronizing the latest code on the page, synchronize the latest code in the local repository
Updating native code (it is recommended that you perform a git pull every time you modify a document) :
```
git pull #If a conflict cannot be merged, resolve the conflict, merge, and resubmit
```

### 6. Git push

```
git push -u origin master
```

### 7. Pull request

Launch PR, request to merge to the dev branch of the source repository, and wait for administrator approval
![image-contributing-view-pr](../.gitbook/assets/image-contributing-view-pr.png)

![image-contributing-new-pr](../.gitbook/assets/image-contributing-new-pr.png)

![image-contributing-create-pr](../.gitbook/assets/image-contributing-create-pr.png)