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

This enables us to interfer with the query to include data from other users, or data that we should not be able to accsess in general. This can also be exploited to manipulate or even delete data from the database.
This dangerous input will for instance drop the entire users table:

```code
http://localhost:3000/users/8 OR1=1; DROP TABLE users--
```
