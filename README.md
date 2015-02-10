# MySQL-crud-API

Simple PHP script that adds a very basic API to a MySQL database

## Requirements

  - PHP 5.3 or higher with MySQLi enabled
  - Apache with mod_rewrite enabled (can also run on Nginx)

## Limitations

  - Public API only: no authentication or authorization
  - Read-only: no write or delete supported
  - No pagination or column selection: always returns full table
  - Single database

## Features

  - Very little code, easy to adapt and maintain
  - Streaming data, low memory footprint
  - Condensed JSON: first row contains field names
  - Optional white- and blacklist support for tables
  - JSONP support for cross-domain requests
  - Combined requests with wildcard support for table names

## Configuration

```
$config = array(
    "hostname"=>"localhost",
    "username"=>"root",
    "password"=>"root",
    "database"=>"blog",
    "whitelist"=>false,
    "blacklist"=>array("users"),
);
```

## Example output

URL: http://localhost/api/cate*

```
{"categories":{"columns":["id","name"],"records":[["1","Internet"],["3","Web development"]]}}
```

## Installation

Put the files in a folder named "api" and edit config.php.dist and rename it to config.php. Let Apache serve the parent folder or configure the .htaccess RewriteBase to match the exposed part of the path.

## License

MIT