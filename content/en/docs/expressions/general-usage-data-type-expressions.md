---
title: General Usage Data Type Expressions
slug: general-usage-data-type-expressions
description: The following data types (dytpes) are available through Analyze to support your requirements
date: 2022-01-25T07:39:53
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


Analyze offers a wide variety of standard data types (dtypes) to support your requirements. As datasets become larger, determining smaller size dtypes for value storage can shrink the size of the table and improve performance. The following dtypes are available: 


* Boolean
* Text
* Numbers


	+ Small Float (6 Digits)
	+ Float (15 Digits)
	+ Small Integer (16 bit) (-32768 to 32767)
	+ Integer (32 bit) (-2147483648 to 2147483647)
	+ Big Integer (64 bit) (-9223372036854775808 to 9223372036854775807)
	+ Numeric
* Dates and Times


	+ Date
	+ Timestamp
	+ Time Interval

It is also possible to convert from one dtype to another using the func.cast() process.



***Note***: Casting to an incompatible dtype may cause errors. For example, casting ‘hello’ to an integer will not work.



# func.cast() Type Conversions




| Analyze Expression | Description | Result |
| func.cast(123, Text) | Integer to Text | ‘123’ |
| func.cast(‘123’, Integer) | Text to Integer | 123 |
| func.cast(‘78.69’, Float) | Text to Float | 78.69 |
| func.cast(‘78.69’, SmallFloat) | Text to Small Float | 78.69 |
| func.cast(‘78.69’, Integer) | Text to Integer (Truncate decimals) | 78 |
| func.cast(‘78.69’, SmallInteger) | Text to Small Integer (Truncate decimals) | 78 |
| func.cast(‘78.69’, BigInteger) | Text to Big Integer (Truncate decimals) | 78 |
| func.cast(1, Boolean) | Integer to Boolean | True |

# func.to() Data Type Conversions




| Analyze Expression | Return Type | Description | Example |
| func.to\_char(timesta mp, text) | text | convert time stamp to string | to\_char(c urrent\_ti mestamp, ‘HH12:MI:S S’) |
| func.to\_char(interva l, text) | text | convert interval to string | to\_char(i nterval ‘15h 2m 12s’, ‘HH24:MI:S S’) |
| func.to\_char(integer , text) | text | convert integer to string | to\_char(1 25, ‘999’) |
| func.to\_char(big float, text) | text | convert real/double precision to string | to\_char(1 25.8::real , ‘999D9’) |
| func.to\_char(numeric , text) | text | convert numeric to string | to\_char(- 125.8, ‘999D99S’) |
| func.to\_date(text, text) | date | convert string to date | to\_date(‘ 05 Dec 2000’, ‘DD Mon YYYY’) |
| func.to\_number(text, text) | numeric | convert string to numeric | to\_number (‘12,454.8 -‘, ‘99G999D9S ‘) |
| func.to\_timestamp(te xt, text) | timestamp with time zone | convert string to time stamp | to\_timest amp(‘05 Dec 2000’, ‘DD Mon YYYY’) |
| func.to\_timestamp(bi g float) | timestamp with time zone | convert UNIX epoch to time stamp | to\_timest amp(200120 400) |

