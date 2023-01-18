# Create/edit pipeline
One of the core pages of the pipeline, the CI pipeline can be generated through the visual interface.
![](../../../.gitbook/assets/image%20%2811%29.png)

1. Assembly line crumbs: There are two click events
   * Click on the pipeline name: Quickly access the pipeline execution history
   * Click the small triangle to the right of the name: Quickly switch to another pipeline
2. Assembly line editing labels, which can switch between assembly line layout pages and basic Settings:
   * Pipeline layout area: see 3
   * Pipeline basic setup:
3. Assembly line arrangement area: abide by [core concept of assembly line](../../../overview/learn-pipeline-in-5-min.md) visual orchestration area
4. Pipeline operation area, including the following common operation set:
   * Save: For each save click, a format version number incremented from 1 is generated, which can be used for rollback
   * Execution: Generates a snapshot pipeline task based on the current orchestration version number
   * Rename: Renames the current pipeline name
   * Favorites: Bookmark the current pipeline, which can be viewed in the My Favorites view
   * Export: Export the current pipeline as JSON, which can be imported when creating a new pipeline (across different projects)
   * Copy to: Copy a new pipeline "old pipeline name \_copy" based on the current orchestration version number of the current pipeline
   * Save as template: Saves the orchestration of the current pipeline as a pipeline template
   * Delete: Soft delete, will be put into the pipeline recycle bin



 #  Next you may need

* [Pipeline execution history](../pipeline-build-history.md)
* [pipeline list page](../pipeline-list.md)
* [pipeline task details page](../pipeline-build-detail/)
