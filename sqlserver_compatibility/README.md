# Table of Contents

<!-- toc -->

- [Microsoft SQL Server compatibility](#microsoft-sql-server-compatibility)
  * [CONVERT_TO_CHAR](#convert_to_char)
  * [CONVERT_TO_DATE](#convert_to_date)
  * [DATEADD](#dateadd)
  * [DATEDIFF](#datediff)
  * [DATENAME](#datename)
  * [DATEPART](#datepart)
  * [EOMONTH](#eomonth)
  * [GETUTCDATE](#getutcdate)
  * [NEWID](#newid)
  * [PATINDEX](#patindex)
  * [JSON_VALUE](../json/README.md#json_value)
  * [ISJSON](../json/README.md#isjson)

<!-- tocstop -->

# Microsoft SQL Server compatibility 

## CONVERT_TO_CHAR
[convert_date_to_char.sql](convert_date_to_char.sql)

 This function is a partial compatibility implementation of MS SQL Server's CONVERT function.
 It converts a date to a string using the specified style.
```sql
CONVERT_TO_CHAR(p_expr IN TIMESTAMP, p_style IN NUMBER ) RETURN VARCHAR(50)
```

## CONVERT_TO_DATE
[convert_to_date.sql](convert_to_date.sql)

This function is a partial compatibility implementation of MS SQL Server's [CONVERT](https://docs.microsoft.com/en-us/sql/t-sql/functions/cast-and-convert-transact-sql) function. It converts a string to a date using the [specified style](https://docs.microsoft.com/en-us/sql/t-sql/functions/cast-and-convert-transact-sql#date-and-time-styles).
```sql
CONVERT_TO_DATE(date_expression VARCHAR(200), style NUMBER ) RETURN DATE
```

## DATEADD
[dateadd.sql](dateadd.sql)

This function is a compatibility implementation of MS SQL Server's [DATEADD](https://docs.microsoft.com/en-us/sql/t-sql/functions/dateadd-transact-sql) function. It adds a specified interval value (as a signed integer) to a specified [datepart](https://docs.microsoft.com/en-us/sql/t-sql/functions/dateadd-transact-sql#arguments) of an input date expression value, and then returns that modified value.
```sql
DATEADD(datepart VARCHAR(11), interval_value NUMBER, date_expression TIMESTAMP) RETURN TIMESTAMP
```

## DATEDIFF
[datediff.sql](datediff.sql)

This function is a compatibility implementation of MS SQL Server's [DATEDIFF](https://docs.microsoft.com/en-us/sql/t-sql/functions/datediff-transact-sql) function. It returns the count (as a signed integer value) of the specified [datepart](https://docs.microsoft.com/en-us/sql/t-sql/functions/datediff-transact-sql#arguments) boundaries crossed between the specified startdate and enddate.
```sql
DATEDIFF(datepart VARCHAR(11), startdate TIMESTAMP, enddate TIMESTAMP) RETURN NUMBER
```

## DATENAME
[datename.sql](datename.sql)

This function is a compatibility implementation of MS SQL Server's [DATENAME](https://docs.microsoft.com/en-us/sql/t-sql/functions/datename-transact-sql) function. It returns a character string representing the specified [datepart](https://docs.microsoft.com/en-us/sql/t-sql/functions/datename-transact-sql#arguments) of the specified date.
```sql
DATENAME(datepart VARCHAR(11), date_expression TIMESTAMP ) RETURN VARCHAR(30)
```

## DATEPART
[datepart.sql](datepart.sql)

This function is a compatibility implementation of MS SQL Server's [DATEPART](https://docs.microsoft.com/en-us/sql/t-sql/functions/datepart-transact-sql) function. It returns an integer representing the specified [datepart](https://docs.microsoft.com/en-us/sql/t-sql/functions/datepart-transact-sql#arguments) of the specified date.
```sql
DATEPART(datepart VARCHAR(11), date_expression TIMESTAMP) RETURN NUMBER
```

## EOMONTH
[eomonth.sql](eomonth.sql)

This function is a compatibility implementation of MS SQL Server's EOMONTH function.
It returns the last day of the month given.
```sql
EOMONTH(date_in IN TIMESTAMP) RETURN DATE
```

## GETUTCDATE
[getutcdate.sql](getutcdate.sql)

This function is a compatibility implementation of MS SQL Server's [GETUTCDATE](https://docs.microsoft.com/en-us/sql/t-sql/functions/getutcdate-transact-sql) function. It returns the current database system timestamp in the UTC (Coordinated Universal Time) time zone.
```sql
GETUTCDATE()
```

## NEWID
[newid.sql](newid.sql)

This function is a compatibility implementation of MS SQL Server's [NEWID](https://docs.microsoft.com/en-us/sql/t-sql/functions/newid-transact-sql) function.  It returns a [version 4 UUID/GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier#Version_4_(random)) (a `uniqueidentifier` equivalent).

Note: As Exasol does not currently support UUID/GUID data type, `CHAR(36)` can be to store such values.
```sql
NEWID()
```

## PATINDEX
[patindex.sql](patindex.sql)

This function is a partial compatibility implementation of MS SQL Server's PATINDEX function.
It returns the startposition of the first occurence of a given pattern in a VARCHAR.
    
```sql
PATINDEX(p_pattern IN VARCHAR2(4000), p_expr IN VARCHAR2(4000)) RETURN NUMBER
```


