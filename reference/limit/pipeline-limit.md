# Pipeline complexity limit

- Each Pipeline contains a maximum of 30 stages
- Each Stage contains a maximum of 30 jobs
- Each Job contains a maximum of 50 tasks
- Each Task contains a maximum of 150 input parameters and 100 output parameters
- Each input parameter also has a corresponding size limit

| Component type | Size limit |
| :------------- | :--------- |
| input          | 1KB        |
| checkbox       | 1KB        |
| textarea       | 16KB       |
| code_editor    | 16KB       |

- Each output parameter has a maximum size of 4KB
