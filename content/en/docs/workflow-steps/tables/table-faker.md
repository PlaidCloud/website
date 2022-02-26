---
title: Table Faker
slug: table-faker
description: This function generates fake data
date: 2022-01-25T07:39:50
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


# Description


Table Faker generates fake data.



## Address




| Generator | Optional Arguments |
| Building Number |  |
| City |  |
| City Suffix |  |
| Country |  |
| Country Code | “representation”=”alpha-2” |
| Full Address |  |
| Latitude |  |
| Longitude |  |
| Military DPO |  |
| Postal Code |  |
| Postal Code Plus 4 |  |
| State |  |
| State Abbreviation |  |
| Street Address |  |
| Street Name |  |
| Street Suffix |  |

## Automotive




| Generator | Optional Arguments |
| License Plate |  |

## Barcode




| Generator | Optional Arguments |
| EAN13 |  |
| EAN8 |  |

## Colors




| Generator | Optional Arguments |
| Color Name |  |
| Hex Color |  |
| RGB Color |  |
| RGB CSS Color |  |
| Safe Color Name |  |
| Safe Hex Color |  |

## Company




| Generator | Optional Arguments |
| Company Catch Phrase |  |
| Company Name |  |
| Company Suffix |  |

## Credit Card




| Generator | Optional Arguments |
| Expriration Date | “start”=”now”“end”=”+10y”# ‘12/20’ |
| Full | “card\_type”=null |
| Number | “card\_type”=null |
| Provider | “card\_type”=null |
| Security Code | “card\_type”=null |

## Currency




| Generator | Optional Arguments |
| Code |  |

## Date Time




| Generator | Optional Arguments |
| AM/PM |  |
| Century |  |
| Date | “pattern”:”%Y-%m-%d”“end\_datetime”:null |
| Date Time | “tzinfo”:null“end\_datetime”=null |
| Date Time this Century | “before\_now”=true“after\_now”=false“tzinfo”=null |
| Date Time this Decade | “before\_now”=true“after\_now”=false“tzinfo”=null |
| Date Time this Month | “before\_now”=true“after\_now”=false“tzinfo”=null |
| Date Time this Year | “before\_now”=true“after\_now”=false“tzinfo”=null |
| Day of Month |  |
| Day of Week |  |
| ISO8601 Date Time | “tzinfo”=null“end\_datetime”=null |
| Month |  |
| Month Name |  |
| Past Date (Last 30 Days) | “start\_date”=”-30d”“tzinfo”=null |
| Timezone |  |
| Unix Time | “end\_datetime”=null“start\_datetime”=null |
| Year |  |

## File




| Generator | Optional Arguments |
| File Extension | “category”=null |
| File Name | “category”=null“extension”=null |
| File Path | “depth”=”1”“category”=null“extension”=null |
| Mime Type | “category”=null |

## Internet




| Generator | Optional Arguments |
| Company Email |  |
| Domain Name |  |
| Domain Word |  |
| Email |  |
| Free Email |  |
| Free Email Domain |  |
| Image URL | “width”=null“height”=null |
| IPv4 | “network”=false“address\_class”=”no”“private”=null |
| IPv6 | “network”=false |
| MAC Address |  |
| Safe Email |  |
| Slug |  |
| TLD |  |
| URI |  |
| URL | “schemes”=null |
| URL Extension |  |
| URL Page |  |
| User Name |  |

## ISBN




| Generator | Optional Arguments |
| ISBN10 | “eparator”=”-“ |
| ISBN13 | “eparator”=”-“ |

## Job




| Generator | Optional Arguments |
| Job Name |  |

## Lorem




| Generator | Optional Arguments |
| Paragraph | “nb\_sentences”=”3”“variable\_nb\_sentences”=true“ext\_word\_list”=null |
| Paragraphs | “nb”=”3”“ext\_word\_list”=null |
| Sentence | “nb\_words”=”6”“variable\_nb\_words”=true“ext\_word\_list”=null |
| Sentences | “nb”=”3”“ext\_word\_list”=null |
| Text | “max\_nb\_chars”=”200”“ext\_word\_list”=null |
| Word | “ext\_word\_list”=null |
| Words | “nb”=”3”“ext\_word\_list”=null |

## Misc




| Generator | Optional Arguments |
| Binary | “length”=”1048576” |
| Boolean | “chance\_of\_getting\_true”=”50” |
| Null Boolean |  |
| Locale |  |
| Language Code |  |
| MD5 | “raw\_output”=false |
| Password | “length”=”10”“special\_chars”=true“digits”=true“upper\_case”=true“lower\_case”=true |
| Random String |  |
| SHA1 | “raw\_output”=false |
| SHA256 | “raw\_output”=false |
| UUID4 |  |

## Numeric




| Generator | Optional Arguments |
| Big Serial (Auto Increment) |  |
| Random Float |  |
| Random Float in Range |  |
| Random Integer |  |
| Random Integer in Range |  |
| Random Numeric |  |
| Random Percentage (0 – 1) |  |
| Random Percentage (0 – 100) |  |
| Serial (Auto Increment) |  |

## Person




| Generator | Optional Arguments |
| First Name |  |
| First Name Female |  |
| First Name Male |  |
| Full Name |  |
| Full Name Female |  |
| Full Name Male |  |
| Last Name |  |
| Last Name Female |  |
| Last Name Male |  |
| Prefix |  |
| Prefix Female |  |
| Prefix Male |  |
| Suffix |  |
| Suffix Female |  |
| Suffix Male |  |

## Phone




| Generator | Optional Arguments |
| Phone Number |  |
| ISDN |  |

## Tax




| Generator | Optional Arguments |
| EIN |  |
| Full SSN |  |
| ITIN |  |

## User Agent




| Generator | Optional Arguments |
| Chrome | “version\_from”=”13”“version\_to”=”63”“build\_from”=”800”“build\_to”=”899” |
| Firefox |  |
| Full User Agent |  |
| Internet Explorer |  |
| Linux Platform Token |  |
| Linux Processor |  |
| Mac Platform Token |  |
| Mac Processor |  |
| Opera |  |
| Safari |  |
| Windows Platform Token |  |

## Special Generators


While these two generators do not have arguments, the options they provide act similarly to arguments.



**Pattern Generator**:




| Number | Format | Output | Description |
| 3.1415926 | {:.2f} | 3.14 | 2 decimal places |
| 3.1415926 | {:+.2f} | +3.14 | 2 decimal places with sign |
| -1 | {:+.2f} | -1.00 | 2 decimal places with sign |
| 2.71828 | {:.0f} | 3 | No decimal places |
| 5 | {:0>2d} | 05 | Pad number with zeros (left padding, width 2) |
| 5 | {:x<4d} | 5xxx | Pad Number with x’s (right padding, width 4) |
| 10 | {:x<4d} | 10xx | Pad number with x’s (right padding, width 4) |
| 1000000 | {:,} | 1,000,000 | Number format with comma separator |
| 0.25 | {:.2%} | 25.00% | Format percentage |
| 1000000000 | {:.2e} | 1.00e+09 | Exponent notation |
| 13 | {:10d} | 13 | Right aligned (default, width 10) |
| 13 | {:<10d} | 13 | Left aligned (width 10) |
| 13 | {:^10d} | 13 | Center aligned (width 10) |

**Random Choice**:


In order to provide the options for random choice, simply put your options in quotes and seperate each option with a comma. So a string of random choice options would appear like this: “x”,”y”,”z”



Here, the “Key Word Args/Pattern/Choices” column of the “pattern” row contains a sentence with several references. The first reference equation ( {percentage0-100:.2f}% ) points to the “percentage0-100” row which will generate a random equation. Therefore, the random percentage produced by the “percentage0-100” row will be automatically inserted into the sentence. The reference equation {first\_name} points to the row titled “first\_name” which will randomly generate a first name, and this name will be automatically inserted into the sentence. The last reference equation ( {randomn\_choice} ) operates the same as the other two.



With this, when the pattern generator is run, you will recieve the following results.

