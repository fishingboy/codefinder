# codefinder

[![Packagist Version](https://img.shields.io/packagist/v/fishingboy/codefinder.svg)](https://packagist.org/packages/fishingboy/codefinder)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

English | [繁體中文](README.zh-TW.md)

codefinder is a lightweight PHP runtime inspection helper. After it is loaded,
it prints the list of included PHP files at the end of the request and provides
a small search form for finding keywords in those files.

## Requirements

- PHP 5.3 or later

## Installation

Install with Composer:

```bash
composer require fishingboy/codefinder
```

## Usage

Load `code_finder.php` in the request you want to inspect:

```php
require_once __DIR__ . '/vendor/fishingboy/codefinder/code_finder.php';
```

When the request finishes, codefinder appends an inspection panel to the page.
Without a keyword, it shows all files returned by `get_included_files()`.
After entering a keyword, it searches both included file paths and file
contents, then displays matching file names and matching lines.

The search form includes a case-insensitive option.

## Notes

- Use this tool only in local development or controlled debugging
  environments.
- Do not enable it in production responses because it can expose file paths,
  source code, request data, and other sensitive information.
- The helper writes HTML directly to the response output.

## License

This project is released under the [MIT License](LICENSE).
