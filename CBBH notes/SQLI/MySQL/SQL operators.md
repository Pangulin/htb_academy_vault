
## AND Operator

the and operator takes two conditions and either returns true or false
the result is only true if both conditions are true

```shell-session
mysql> SELECT 1 = 1 AND 'test' = 'test';

+---------------------------+
| 1 = 1 AND 'test' = 'test' |
+---------------------------+
|                         1 |
+---------------------------+
1 row in set (0.00 sec)

mysql> SELECT 1 = 1 AND 'test' = 'abc';

+--------------------------+
| 1 = 1 AND 'test' = 'abc' |
+--------------------------+
|                        0 |
+--------------------------+
1 row in set (0.00 sec)
```

------
## OR

it takes the two conditions and returns true if one of both conditions is met 

```shell-session
mysql> SELECT 1 = 1 OR 'test' = 'abc';

+-------------------------+
| 1 = 1 OR 'test' = 'abc' |
+-------------------------+
|                       1 |
+-------------------------+
1 row in set (0.00 sec)

mysql> SELECT 1 = 2 OR 'test' = 'abc';

+-------------------------+
| 1 = 2 OR 'test' = 'abc' |
+-------------------------+
|                       0 |
+-------------------------+
1 row in set (0.00 sec)
```

---
## Not

the not operator simply switches the output of a statement 


```shell-session
mysql> SELECT NOT 1 = 1;

+-----------+
| NOT 1 = 1 |
+-----------+
|         0 |
+-----------+
1 row in set (0.00 sec)

mysql> SELECT NOT 1 = 2;

+-----------+
| NOT 1 = 2 |
+-----------+
|         1 |
+-----------+
1 row in set (0.00 sec)
```



-----
## Symbol Operators

These operators can also be represented using symbols 

AND = && 

OR = || 

NOT = ! 

```shell-session
mysql> SELECT 1 = 1 && 'test' = 'abc';

+-------------------------+
| 1 = 1 && 'test' = 'abc' |
+-------------------------+
|                       0 |
+-------------------------+
1 row in set, 1 warning (0.00 sec)

mysql> SELECT 1 = 1 || 'test' = 'abc';

+-------------------------+
| 1 = 1 || 'test' = 'abc' |
+-------------------------+
|                       1 |
+-------------------------+
1 row in set, 1 warning (0.00 sec)

mysql> SELECT 1 != 1;

+--------+
| 1 != 1 |
+--------+
|      0 |
+--------+
1 row in set (0.00 sec)
```

---

## Operators in queries 

this is an example that lists all usernames that are NOT john 

```shell-session
mysql> SELECT * FROM logins WHERE username != 'john';
```

you can combine such statements using AND 

```shell-session
mysql> SELECT * FROM logins WHERE username != 'john' AND id > 1;
```

here every user with an id higher than 1 and NOT the username john gets selected 

----

## Multiple Operator Precedence

Here is a list of common operations and their precedence, as seen in the [MariaDB Documentation](https://mariadb.com/kb/en/operator-precedence/)

- Division (`/`), Multiplication (`*`), and Modulus (`%`)
- Addition (`+`) and subtraction (`-`)
- Comparison (`=`, `>`, `<`, `<=`, `>=`, `!=`, `LIKE`)
- NOT (`!`)
- AND (`&&`)
- OR (`||`)

This list has a priority from top to bottom 

so in a query like: 

```sql
SELECT * FROM logins WHERE username != 'tom' AND id > 3 - 2;
```

the first thing that gets evaluated is the 3-2 wich equals to 1 
then its the comparison > and != will be evaluated togheter and last but not least the AND 