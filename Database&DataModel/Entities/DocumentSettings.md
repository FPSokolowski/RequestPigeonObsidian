## Description  
Settings for documents. One record per [[DocumentType]] - each type can have different rules.
  
## Columns  
| Name                             | Type .NET                                | Type DB                                              | Nullable | Description                                                                                                                                                          | Notes                                   |
| -------------------------------- | ---------------------------------------- | ---------------------------------------------------- | :------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------- |
| Id                               | Guid                                     | uniqueidentifier                                     |    ❌     | Primary key                                                                                                                                                          | PK //or maybe Type is sufficient as PK? |
| Type                             | [[DocumentType]]                         | `= [[Database&DataModel/Enums/DocumentType]].dbType` |    ❌     | Document Type                                                                                                                                                        |                                         |
| Header                           | string                                   | nvarchar(128)                                        |    ❌     | Document's header                                                                                                                                                    |                                         |
| DefaultTextContent               | string                                   | nvarchar(2048)                                       |    ✔     | Optional text (specification / explaination / reason / purpose / additional notes)                                                                                   |                                         |
| StrictAcceptancePolicy           | bool                                     | bit                                                  |    ❌     | General rule: keep acceptance policy strict. If true all overrides are forbidden.                                                                                    | Default: FALSE                          |
| SameLevelForbidden               | bool                                     | bit                                                  |    ❌     | Allow managers of the same level to accept requests from their subordinates.                                                                                         | Default: TRUE                           |
| AllowOverrideAcc eptanceByHigher | bool                                     | bit                                                  |    ❌     | Allow higher manager/boss to change decision of lower level manager.                                                                                                 | Default: TRUE                           |
| AllowDelegateDecission           | bool                                     | bit                                                  |    ❌     | Allow approval person to pass this decision to another one.                                                                                                          | Default: TRUE                           |
| AcceptanceRules                  | List<[[DocumentSettingsAcceptanceRule]]> | --                                                   |    ❌     | Required acceptances rules. It sets general rules for example: for Purchase on IT category 2 acceptances are required: one IT supervisor, second requestor's manager | *relationship*                          |
| ==[[BaseEntity]]==               | --                                       | --                                                   |    --    | Columns inherited from [[BaseEntity]] class.                                                                                                                         | --                                      |
  
## Relationships  
- One-to-many with [[DocumentSettingsAcceptanceRule]]
  
## Indexes  
- IX_DocumentTypeSettings_Type (Unique) 
  
## Notes  
* Should be cached. 
* At first phase this one will not be available for user via UI