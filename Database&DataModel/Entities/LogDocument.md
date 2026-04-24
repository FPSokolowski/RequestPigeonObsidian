## Description  
Logger of documents history (create, status change, modifications).
  
## Columns  
| Name               | Type .NET             | Type DB                         | Nullable | Description                                                                     | Notes |
| ------------------ | --------------------- | ------------------------------- | -------- | ------------------------------------------------------------------------------- | ----- |
| Id                 | Guid                  | uniqueidentifier                | ❌        | Id                                                                              |       |
| DocumentId         | Guid                  | uniqueidentifier                | ✔        | Null for non related to specific document (for example general settings change) | FK    |
| EventType          | [[DocumentEventType]] | `=[[DocumentEventType]].dbType` | ❌        | Type of event                                                                   |       |
| UserId             | Guid                  | uniqueidentifier                | ✔        |                                                                                 | FK    |
| WhatChanged        | string                | nvarchar(64)                    | ✔        |                                                                                 |       |
| ValueAfter         | string                | nvarchar(512)                   | ✔        |                                                                                 |       |
| StatusBefore       | [[DocumentStatus]]    | `=[[DocumentStatus]].dbType`    | ✔        |                                                                                 |       |
| StatusAfter        | [[DocumentStatus]]    | `=[[DocumentStatus]].dbType`    | ✔        |                                                                                 |       |
| Info               | string                | nvarchar(256)                   | ✔        | Additional info/comment                                                         |       |
| ==[[BaseEntity]]== | --                    | --                              | --       | Columns inherited from [[BaseEntity]] class.                                    |       |
  
## Relationships  
* Many-to-one with [[Document]]
* Many-to-one with [[User]]

## Indexes  
* IX_LogDocument_CreatedAt
## Notes  