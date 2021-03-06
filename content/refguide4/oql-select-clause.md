---
title: "OQL Select Clause"
parent: "oql"
---
The SELECT clause specifies which entity attributes or other specified data must be retrieved. The SELECT clause consists of the term SELECT and one or more expressions. These expressions must be separated by a comma. Each expression defines a column in the result.
Each expression can have an alias, which will be the name of the column in the result.

The syntax is the following:

```
SELECT [ DISTINCT ]
    {
            *
        | { entity_name | from_alias }.*
        | { expression [ [ AS ] column_alias ] } [ ,...n ]
    }

```

**DISTINCT**
Specifies that double rows must not be shown in the result.

*** (asterisk)**
Specifies that all attributes from all entities in the FROM clause should be returned.

**entity_name.***, **from_alias.***
Specifies that all attributes of the specified entity or expression of the FROM clause should be returned.

```
SELECT Sales.Customer.* FROM Sales.Customer
```

```
SELECT Person.* FROM Sales.Customer AS Person
```

**expression**
Is either a constant, a function or any combination of attribute names, constants, and functions connected by operator(s) or a subquery. When you add more expressions, place a comma between each expression.

```
SELECT Name AS CustomerName, LastName AS CustomerLastName, Birthday, Category FROM Sales.Customer
```

See [this page](oql-expressions) for more information.

**column_alias**
Is an alternative name to replace the column name in the result. When the attribute Name is retrieved, the result column is 'Name'. With an alias, you can specify another result column name, like 'Customer Name'. An alias can contain spaces.

```
SELECT Sales.Customer.Name AS CustomerName FROM Sales.Customer
```

```
SELECT Sales.Customer.Name AS 'Customer Name' FROM Sales.Customer
```
