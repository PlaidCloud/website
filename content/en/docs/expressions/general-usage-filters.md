---
title: General Usage Filters
slug: general-usage-filters
description: Apply filters using column references
date: 2022-01-25T07:39:53
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


You may apply filters using column references.




| Operator | Description | Example |
| and\_() | Creates an AND SQL condition | and\_(table.a > 23, table.b == u’blue’) |
| or\_() | Creates an OR SQL condition | or\_(table.a > 23, table.b == u’blue’) |
| not\_() | Inverts the condition | not\_(and\_(table.a > 23, table.b == u’blue’)) |
| in\_() | Test if values are with a tuple of values | table.column.in\_((1, 2, 3)) |
| notin | Inverts the IN condition | table.column.notin((1, 2, 3)) |
| any\_() | Applies the SQL ANY() condition to a column | table.column.any((‘red’, ‘blue’, ‘yellow’)) |
| between | Applies the SQL BETWEEN condition | table.column.between(23, 46) |
| startswith | Applies the SQL LIKE ‘%’ | table.column.startswith(‘abc’) |
| contains | Applies the SQL LIKE ‘%%’ | table.column.contains(‘mno’) |
| endswith | Applies the SQL LIKE ‘%%’ | table.column.endswith(‘xyz’) |
| is\_ | Applies the SQL is the IS for things like IS NULL | table.column.is\_(None) |
| isnot | Applies the SQL is the IS for things like IS NOT NULL | table.column.isnot(None) |
| like | Applies the SQL LIKE method | table.column.like(‘%foobar%’’) |
| table.column. like(‘% /% of profit%’, escape=’/’) |  |  |
| notlike | Applies the SQL NOT LIKE method | table.column.notlike(‘%foobar%’) |
| table.column. notlike(‘% /% of profit%’, escape=’/’) |  |  |
| ilike | Applies the SQL ILIKE method | table.column.ilike(‘%foobar%’) |
| table.column. like(‘% /% of profit%’, escape=’/’) |  |  |
| notilike | Applies the SQL NOT ILIKE method | table.column.notilike(‘%foobar%’) |
| table.column. notilike(‘% /% of profit%’, escape=’/’) |  |  |
| NULL, Null, null | Alias for Python None |  |
| TRUE, true | Alias for Python True |  |
| FALSE, false | Alias for Python False |  |
| > | Greater Than | table.column > 23 |
| < | Less Than | table.column < 23 |
| >= | Greater than or equal to | table.column >= 23 |
| <= | Less than or equal to | table.column <= 23 |
| == | Equal | table.column == 23 table.column == ‘blue’ |
| != | Not Equal | table.column != 23 table.column != ‘blue’ |

