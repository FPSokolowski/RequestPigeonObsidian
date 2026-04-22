## Description  
Relationship table. Handles many-to-many relationship between tables Documents and Acceptances.
  
## Columns  
| Name               | Type .NET | Type DB          | Nullable | Description                                  | Notes |
| ------------------ | --------- | ---------------- | :------: | :------------------------------------------- | ----- |
| Id                 | Guid      | uniqueidentifier |    ❌     |                                              | PK    |
| DocumentId         | Guid      | uniqueidentifier |    ❌     |                                              | FK    |
| AcceptanceId       | Guid      | uniqueidentifier |    ❌     |                                              | FK    |
| ==[[BaseEntity]]== | ---       | ---              |   ---    | Columns inherited from [[BaseEntity]] class. | ---   |
  
## Relationships  
  * The table connects Documents and Acceptances tables.
## Indexes  
- automatically EF Core index FK's 
  
## Notes  
