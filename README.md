# CreateMySqlSchemaFromJSON

Build MySql by loading the JSON files individually or group of files from a Directory

## Shell

`php -q /path/to/CreateSchemaFromJSON.php "mysql:dbname=MyDB;host=localhost;port=3306" "user" "password" "/path/to/json/schema/directory"` 

## PHP
```
// Instanciate PDO
$pdo = new PDO("mysql:dbname=MyDB;host=localhost;port=3306", "user", "password");
// Instanciate CreateSchemaFromJSON
$sqlSchema = new CreateSchemaFromJSON($pdo);
// Generate tables from all .json files in a directory
$sqlSchema->CreateTableFromDirFiles("/path/to/json/schema/directory");
// Or, generate table from a single .json file
$sqlSchema->CreateTableFromSingleFile("/path/to/schema.json");
```