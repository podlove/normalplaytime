# Normal Play Time Parser

[![Build Status](https://travis-ci.org/podlove/normalplaytime.png?branch=master)](https://travis-ci.org/podlove/normalplaytime)

PHP parser for Normal Play Time (RFC 2326)

- http://www.ietf.org/rfc/rfc2326.txt
- http://www.w3.org/TR/media-frags/#npttimedef

## Usage

```php
use \Podlove\NormalPlayTime\Parser;

$parser = new Parser();

// get seconds or milliseconds
$parser->parse("1.834");      // 1834
$parser->parse("1.834", "s"); // 1

// invalid returns NULL
$parser->parse("abc"); // NULL

// valid example NPT strings
$parser->parse("1");        // 1000
$parser->parse("12:34");    // 754000
$parser->parse("12:34.56"); // 754560
$parser->parse("1:2");      // 62000
$parser->parse("1:2:3.4");  // 3723400
```