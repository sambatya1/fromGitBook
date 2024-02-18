# Изучаем SQL

Дата записи: 03.02.2015

## Как проверить существование БД в СУБД MS SQL Server?

### Способ №1

```sql
 if db_id ('[имя_БД]') is null 
 ```

### Способ №2

```sql
Select db_id ('name')
 ```

### Способ №3

```sql
  IF EXIST (Select * From master.sysdatabases)
  WHERE name =N'<database_name, sysname,testdb>' 
  DROP database <database_name, sysname, test_db>
```

### Способ №4

```sql
sp_databases 
SQLDataReader ("DATABASE_NAME")
```

### Способ №5

```sql
SELECT count(name) FROM sysdatabases 
WHERE [name] = command.ExecuteScalar
```

### Способ №6

```sql
SELECT name FROM master.dbo.sysdatabases 
WHERE ('['+name+']'=N'Test')
```
