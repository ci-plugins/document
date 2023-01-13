# Plug-in publishing specification

## Publish the package specification
* The release package is a zip file
* The release package includes:
  * \[Mandatory \] Plug-in executable file
  * \[Mandatory \] task.json
  * \[Optional \] frontend directory
    The * directory contains customized UI-related files
## Version management specification
* Version number management follows the Semantic Version(https://semver.org/) specification
* Users can reference the plug-in in the pipeline using the mode \[major version.latest \] to automatically use the latest version under the specified major version number. Upgrade the plug-in according to the specifications.
