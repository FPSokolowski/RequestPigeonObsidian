## Description  
Acceptance is a link between document and assigned decision-makers. One document can have one or more assigned acceptances. 
Next step is to give special rights for big fishes to override decisions of employees lower in organizational hierarchy (for example an owner should have a possibility to change decision of a manager and his (the owner) decision should be a final one(directly impact document status)). It will be helpful especially if second tier manager is absent and higher manager should have possibility to accept urgent requests.
  
## Columns  
| Name               | Type .NET    | Type DB          | Nullable | Description                                                                                                  | Notes |
| ------------------ | ------------ | ---------------- | :------: | :----------------------------------------------------------------------------------------------------------- | ----- |
| Id                 | Guid         | uniqueidentifier |    ❌     | Primary key                                                                                                  | PK    |
| DateTimeIssued     | DateTime     | datetime2(0)     |    ✔     | Date time issued (when an acceptance was assigned to document (so when the request appeared at his/her app)) |       |
| DateTimeDecision   | DateTime     | datetime2(0)     |    ✔     | Date time of a first decision                                                                                |       |
| Decision           | [[Decision]] | nvarchar(16)     |    ❌     | Decision's result                                                                                            |       |
| TextNote           | string       | nvarchar(1024)   |    ✔     | Optional note (for example reason or legal basis)                                                            |       |
| ==[[BaseEntity]]== | ---          | ---              |   ---    | Columns inherited from [[BaseEntity]] class.                                                                 | ---   |
  
## Relationships  
- One-to-one with [[User]]
  
## Indexes  
- IX_Document_Type 
  
## Notes  
- 