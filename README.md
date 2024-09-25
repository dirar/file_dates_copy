# File Dates Copy

This project contains two Python scripts for managing file metadata using an SQLite database. The first script collects file created and modified date and stores it in an SQLite database, while the second script updates another/same files timestamps based on the stored filename. This script is useful when you need to replicate file timestamps in another location with the same filenames and directory structure, without actually copying the files



## Table of Contents

- [Installation](#installation)

- [Usage](#usage)

  - [extract_dates_to_db.py](#extract_dates_to_db.py)

  - [set_files_date.py](#update_file_timestampspy)

- [License](#license)



## Installation



1. Clone the repository:

   ```sh

   git clone https://github.com/yourusername/yourrepository.git

   cd yourrepository

   ```



2. Create a virtual environment (optional but recommended):

   ```sh

   python3 -m venv venv

   source venv/bin/activate   # On Windows use \`venv\\Scripts\\activate\`

   ```



3. Install the required dependencies:

   ```sh

   pip install -r requirements.txt

   ```



## Usage



### extract_dates_to_db.py



This script traverses a directory, collects file metadata (such as creation and modification times), and stores this data in an SQLite database.



#### Syntax

```sh

python extract_dates_to_db.py /path/to/directory --db custom_db_name.db

```



#### Parameters

- \`/path/to/directory\`: The directory to traverse.

- \`--db custom_db_name.db\`: (Optional) The SQLite database file name. Defaults to \`file_data.db\`.



#### Example

```sh

python extract_dates_to_db.py /home/user/documents --db my_file_data.db

```



### set_files_date.py



This script updates the timestamps of files in a directory based on the metadata stored in an SQLite database and logs any discrepancies.



#### Syntax

```sh

python set_files_date.py /path/to/directory --db custom_db_name.db

```



#### Parameters

- \`/path/to/directory\`: The directory to traverse.

- \`--db custom_db_name.db\`: (Optional) The SQLite database file name. Defaults to \`files.db\`.



#### Example

```sh

python set_files_date.py /home/user/documents --db my_file_data.db

```



## License



This project is licensed under the MIT License.