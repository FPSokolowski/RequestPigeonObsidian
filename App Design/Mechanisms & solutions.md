## Cache
Implement cache memory for constant values stored in db (const values, content of selects). Use cache politics for them.

## EF Core Interceptors
Described at [[DB Rules&Conventions]].

## DateTime
UTC DateTime should be stored in DB and it should be used at backend but UI needs always conversion to Local DateTime


## ControllerCustom
There should be one abstract ControllerCustom which should be inherited by all Controllers. It will contain common methods/interceptors/fields to handle features like: remember previous urls, simplify alerts handling(also handle redirections), take user info from cookie and store it. 
