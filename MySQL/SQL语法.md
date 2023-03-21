# SQL基本语法

## UPDATE

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

## DELETE

```sql
DELETE t1 FROM t1 LEFT JOIN t2 ON t1.id=t2.id WHERE t2.id IS NULL;
```

## LEFT JOIN

```sql
SELECT column1, column2, ...
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

## IF

```sql
SELECT
    IF(column1 > 50000, column1, 0) AS 'column2'
FROM
    table1
```

## CASE

在 SQL 中，CASE 表达式用于根据条件对数据进行条件性的操作。它可以在 SELECT、WHERE 和 ORDER BY 等语句中使用。

```sql
CASE expression
    WHEN value_1 THEN result_1
    WHEN value_2 THEN result_2
    ...
    ELSE default_result
END
```

其中，expression 是要进行判断的表达式，value_1、value_2 等是要匹配的值，result_1、result_2 等是匹配成功后要返回的结果，default_result 是当所有条件都不匹配时要返回的结果。

## LIKE

`LIKE` 是一种在 SQL 查询中用于模式匹配的操作符，它可以用于从一个表格中选择特定的行。`LIKE` 操作符用于在 WHERE 子句中指定一个模式，并从一个表格中选择匹配该模式的行。

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name LIKE pattern;
```

在上面的语法中，`column_name(s)` 是要检索的列名，`table_name` 是要检索的表格名，`pattern` 是指定要匹配的字符串模式。 `pattern` 中可以包含以下两种通配符：

- `%`：表示零个或多个字符

- `_`：表示一个单个字符

我们可以使用通配符来查找匹配特定模式的字符串。例如，以下查询将返回所有包含 "abc" 子字符串的行：

```sql
SELECT * FROM customers WHERE first_name LIKE '%abc%';
```

## UNION与UNION ALL

### UNION

`UNION` 运算符用于合并两个 SELECT 语句的结果集，并消除重复行。如果 SELECT 语句中有重复行，则只会包含一次该行。以下是 `UNION` 运算符的语法：

```sql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

### UNION ALL

`UNION ALL` 运算符也用于合并两个 SELECT 语句的结果集，但它不会消除重复行。它将返回两个查询的所有行，包括重复的行。以下是 `UNION ALL` 运算符的语法：

```sql
SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2;
```

## LIMIT

`LIMIT` 是一个用于在 SQL 查询中指定返回行数的子句。`LIMIT` 子句可以在 SELECT 语句的末尾使用，并在其中指定要返回的行数。以下是 `LIMIT` 子句的基本语法：

```sql
SELECT column_name(s) FROM table_name LIMIT number_of_rows;
```

在上面的语法中，`column_name(s)` 是要从表格中选择的列名，`table_name` 是要从中检索数据的表格名称，`number_of_rows` 是要返回的行数。

## OFFSET

`OFFSET` 子句是一个可选的用于在 SQL 查询中指定要从结果集的开头跳过的行数的子句。它通常与 `LIMIT` 子句一起使用，以从查询结果集的任意位置开始返回一定数量的行。以下是 `OFFSET` 子句的基本语法：

```sql
SELECT column_name(s) FROM table_name LIMIT number_of_rows OFFSET offset_number;
```

在上面的语法中，`column_name(s)` 是要从表格中选择的列名，`table_name` 是要从中检索数据的表格名称，`number_of_rows` 是要返回的行数，而 `offset_number` 是要从结果集的开头跳过的行数。

## 函数

### CONCAT

该函数用于将两个或多个字符串连接起来，形成一个更长的字符串。

```sql
SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM customers;
```

### UPPER

该函数将一个字符串中的所有字符转换为大写形式。

```sql
SELECT UPPER(first_name) AS upper_name FROM customers;
```

### LOWER

该函数将一个字符串中的所有字符转换为小写形式。

```sql
SELECT LOWER(first_name) AS lower_name FROM customers;
```

### LEFT

该函数用于提取一个字符串中最左边的字符。

```sql
SELECT LEFT(phone_number, 4) AS front_four_digits FROM customers;
```

### RIGHT

该函数用于提取一个字符串中最右边的字符。使用字符串函数 `LEN` 来获取字符串长度。

```sql
SELECT RIGHT(phone_number, LENGTH(phone_number) - 4) AS right_remainder FROM customers;
```

### GROUP_CONCAT

```sql
SELECT GROUP_CONCAT(DISTINCT column1 ORDER BY column2 ASC SEPARATOR ',')
FROM table_name
WHERE condition
GROUP BY group_column;
```

