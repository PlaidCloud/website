---
title: General Usage Dates and Time Expressions
slug: general-usage-dates-and-time-expressions
description: Common Expression Values for date/time functions
date: 2022-01-25T07:39:53
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---




| Analyze Expression | Return Type | Description | Example | Result |
| func.age(timestamp, timestamp) | interval | Subtract arguments, producing a “symbolic” result that uses years and months | age (timest amp ‘2001-04-1 0’, timestamp ‘1957-06-1 3’) | 43 years 9 months 27 days |
| func.age(timestamp) | interval | Subtract from current\_date | age(timest amp ‘1957-06-1 3’) | 43 years 8 months 3 days |
| func.clock\_timestamp () | timestamp with time zone | Current date and time (changes during statement execution) |  |  |
| func.current\_date | date | Current date |  |  |
| func.current\_time | time with time zone | Current time of day |  |  |
| func.current\_timesta mp | timestamp with time zone | Current date and time (start of current transaction) |  |  |
| func.date\_part(text, timestamp) | double precision | Get subfield (equivalent to extract) | date\_part (‘hour’, timestamp ‘2001-02-1 6 20:38:40’) | 20 |
| func.date\_part(text, interval) | double precision | Get subfield (equivalent to extract) | date\_part (‘month’, interval ‘2 years 3 months’) | 3 |
| func.date\_trunc(text , timestamp) | timestamp | Truncate to specified precision | date\_trun c(‘hour’, timestamp ‘2001-02-1 6 20:38:40’) | 36938.833 3333333 |
| func.extract(field from timestamp) | double precision | Get subfield | extract(ho ur from timestamp ‘2001-02-1 6 20:38:40’) | 20 |
| func.extract(field from interval) | double precision | Get subfield | extract(mo nth from interval ‘2 years 3 months’) | 3 |
| func.isfinite(timesta mp) | boolean | Test for finite time stamp (not equal to infinity) | isfinite(t imestamp ‘2001-02-1 6 21:28:30’) | TRUE |
| func.isfinite(interva l) | boolean | Test for finite interval | isfinite(i nterval ‘4 hours’) | TRUE |
| func.justify\_days(in terval) | interval | Adjust interval so 30-day time periods are represented as months | justify\_d ays(interv al ‘30 days’) | 1 month |
| func.justify\_hours(i nterval) | interval | Adjust interval so 24-hour time periods are represented as days | justify\_h ours(inter val ‘24 hours’) | 1 day |
| func.justify\_interva l(interval) | interval | Adjust interval using justify\_days and justify\_hours , with additional sign adjustments | justify\_i nterval(in terval ‘1 mon -1 hour’) | 29 days 23:00:00 |
| func.now() | timestamp with time zone | Current date and time (start of current transaction) |  |  |
| func.statement\_times tamp() | timestamp with time zone | Current date and time (start of current statement) |  |  |
| func.timeofday() | text | Current date and time (like clock\_timesta mp, but as a text string) |  |  |
| func.transaction\_tim estamp() | timestamp with time zone | Current date and time (start of current transaction) |  |  |

## Date and Time Formatting Directives




| Pattern | Description |
| HH | hour of day (01-12) |
| HH12 | hour of day (01-12) |
| HH24 | hour of day (00-23) |
| MI | minute (00-59) |
| SS | second (00-59) |
| MS | millisecond (000-999) |
| US | microsecond (000000-999999 ) |
| SSSS | seconds past midnight (0-86399) |
| AM or A.M. or PM or P.M. | meridian indicator (uppercase) |
| am or a.m. or pm or p.m. | meridian indicator (lowercase) |
| Y,YYY | year (4 and more digits) with comma |
| YYYY | year (4 and more digits) |
| YYY | last 3 digits of year |
| YY | last 2 digits of year |
| Y | last digit of year |
| IYYY | ISO year (4 and more digits) |
| IYY | last 3 digits of ISO year |
| IY | last 2 digits of ISO year |
| I | last digits of ISO year |
| BC or B.C. or AD or A.D. | era indicator (uppercase) |
| bc or b.c. or ad or a.d. | era indicator (lowercase) |
| MONTH | full uppercase month name (blank-padded to 9 chars) |
| Month | full mixed-case month name (blank-padded to 9 chars) |
| month | full lowercase month name (blank-padded to 9 chars) |
| MON | abbreviated uppercase month name (3 chars) |
| Mon | abbreviated mixed-case month name (3 chars) |
| mon | abbreviated lowercase month name (3 chars) |
| MM | month number (01-12) |
| DAY | full uppercase day name (blank-padded to 9 chars) |
| Day | full mixed-case day name (blank-padded to 9 chars) |
| day | full lowercase day name (blank-padded to 9 chars) |
| DY | abbreviated uppercase day name (3 chars) |
| Dy | abbreviated mixed-case day name (3 chars) |
| dy | abbreviated lowercase day name (3 chars) |
| DDD | day of year (001-366) |
| DD | day of month (01-31) |
| D | day of week (1-7; Sunday is 1) |
| W | week in month (1-5) (The first week starts on the first day of the month.) |
| WW | week number in year (1-53) (The first week starts on the first day of the year.) |
| IW | ISO week number of year (The first Thursday of the new year is in week 1.) |
| CC | century (2 digits) |
| J | Julian Day (days since January 1, 4712 BC) |
| Q | quarter |
| RM | month in Roman numerals (I-XII; I=January) (uppercase) |
| rm | month in Roman numerals (i-xii; i=January) (lowercase) |
| TZ | time-zone name (uppercase) |
| tz | time-zone name (lowercase) |

