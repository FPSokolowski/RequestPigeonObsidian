## Description  
Connection between [[User]] and [[Claim]]s. For now it handles only simple 2 states: connected (true) and not connected (false).
## Columns  
| Name               | Type .NET | Type DB          | Nullable | Description                                      | Notes |
| ------------------ | --------- | ---------------- | :------: | :----------------------------------------------- | ----- |
| Id                 | Guid      | uniqueidentifier |    ❌     | Primary key //is this necessary? Probably not... | PK    |
| UserId             | Guid      | uniqueidentifier |    ❌     | User                                             | FK    |
| ClaimId            | Guid      | uniqueidentifier |    ❌     | Claim                                            | FK    |
| ==[[BaseEntity]]== | --        | --               |    --    | Columns inherited from [[BaseEntity]] class.     | --    |
  
## Relationships  
- One-to-one with [[User]]
- One-to-one with [[Claim]]
## Indexes  
## Notes  
* Next step: add also a field Value to handle various claim types (as json-like string) with automatic parsing.