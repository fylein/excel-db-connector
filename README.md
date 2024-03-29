# Excel Database Connector
Connects Excel to a database connector to transfer information to and fro. [Fyle](https://www.fylehq.com/) is an expense management system.

## Installation

This project requires [Python 3+](https://www.python.org/downloads/).

1. Download this project and use it (copy it in your project, etc).
2. Install it from [pip](https://pypi.org).

        $ pip install excel-db-connector

## Usage

This connector is very easy to use.
1. First you'll need to create a connection using the main class FyleSDK.
```python
import sqlite3

from excel_db_connector import ExcelConnector

dbconn = sqlite3.connect('/tmp/temp.db')


excel_connector = ExcelConnector(dbconn)

```
2. After that you'll be able to extract data from excel and store it in the db
```python
# Create the tables to for all objects
excel_connector.create_tables('/tmp/create_tables.sql')

excel_connector.extract('excel.xlsx', 'table_name')
```

## Contribute

To contribute to this project follow the steps

* Fork and clone the repository.
* Run `pip install -r requirements.txt`
* Setup pylint precommit hook
    * Create a file `.git/hooks/pre-commit`
    * Copy and paste the following lines in the file - 
        ```bash
        #!/usr/bin/env bash 
        git-pylint-commit-hook
        ```
     * Run `chmod +x .git/hooks/pre-commit`
## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

