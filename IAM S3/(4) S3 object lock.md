### S3 object Lock
* write once, read many (WORM) model
* extra layer of protection

2 different modes:
* #### governance mode:
  * users can't overwrite or delete an oject version or alter it's lock settings
  * but, you can grant some users to permissions to alter retention settings
* #### compliance mode:
  * can't be overwritten or deleted by any user (even root user)

#### Retention period:
* Protects an object version for a fixed amount of time
* After it expires object version can be overwritten or deleted unless you place a legal hold.

#### Legal Hold:
* Prevents an object version from being overwritten or deleted
* It does not have an associated retention period, remains ineffect until removed
* Can be freely placed and removed by any user with IAM s3 legalhold permission

### Glacier Vault Lock:
