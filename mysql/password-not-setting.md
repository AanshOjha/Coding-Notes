## Error
```
mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
ERROR 1819 (HY000): Your password does not satisfy the current policy requirements
```
## Solution
```
SHOW VARIABLES LIKE 'validate_password%';
```
Change them as you like
```
SET GLOBAL validate_password.length = 8;
SET GLOBAL validate_password.mixed_case_count = 1;
SET GLOBAL validate_password.number_count = 1;
SET GLOBAL validate_password.special_char_count = 1;
SET GLOBAL validate_password.policy = 'MEDIUM';
ALTER USER 'root'@'localhost' IDENTIFIED BY 'new_password';
FLUSH PRIVILEGES;
exit;
```
