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



