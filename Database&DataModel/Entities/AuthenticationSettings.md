## Description  
Authentication global settings. Single-record table!

## Columns  
| Name                | Type .NET | Type DB          | Nullable | Description                                                          | Notes                                          |
| ------------------- | --------- | ---------------- | :------: | :------------------------------------------------------------------- | ---------------------------------------------- |
| Id                  | Guid      | uniqueidentifier |    ❌     | Primary key                                                          | PK                                             |
| LockoutAfterXFailed | int       | int              |    ✔     | Lock after X failed login tries. Disable (set null) is **dangerous** | Default: 5. If null then feature is turned off |
| LockoutTime         | Timestamp | timestamp        |    ❌     | Lockout time after X failed login tries                              | Default: 5 minutes                             |
| ==[[BaseEntity]]==  | --        | --               |    --    | Columns inherited from [[BaseEntity]] class                          | --                                             |
  
## Relationships  
  
## Indexes  
  
## Notes  
* Single-record table