===============
Data File Utils
===============

Collection of Python scripts/utils for file manipulation tasks.


Exported console scripts
------------------------

The following exported console scripts are available:

- analyze-record-tuples
- archive-dir
- backup-dir
- backup-file
- compare-tab-files
- create-tmp-dir
- delete-old-files
- find-last-directory
- find-last-file
- jsonl2json
- profile-data-file
- tsv2json
- xlsx2tsv


analyze-record-tuples
---------------------

This script will determine which records are missing from either of the two tab-delimited files. Some specified number of columns will make up the unique tuple
for each line/record.


archive-dir
-----------

This script will archive the directory in-place using tar -zcvf and will apply suffix TIMESTAMP.tgz to the directory.

Sample invocation:

.. code-block:: shell

    archive-dir /tmp/test-123/test-abc
    test-abc/
    test-abc/file-1
    test-abc/file-2
    test-abc/file-3
    test-abc/file-4
    Directory '/tmp/test-123/test-abc' successfully archived to 'test-abc_2024-01-02-212243.tgz'

backup-dir
----------

This script will backup the directory in-place and will apply suffix TIMESTAMP.bak to the directory.

Sample invocation:

.. code-block:: shell

    backup-dir /tmp/test-123
    Backed-up '/tmp/test-123' to '/tmp/test-123.2024-01-02-210517.bak'


backup-file
-----------

This script will backup the file in-place and will apply suffix TIMESTAMP.bak to the file.

Sample invocation:

.. code-block:: shell

    backup-file setup.py
    Backed-up 'setup.py' to 'setup.py.2024-01-02-205756.bak'


compare-tab-files
-----------------

This script will parse two tab-delimited files and generate a report to indicate which lines and columns are different.

create-tmp-dir
--------------

This script will prompt the user for the following information and then create a temporary directory:
- root directory (default is /tmp)
- user directory (default is $USER)
- purpose

Sample invocation:

.. code-block:: shell

    create-tmp-dir
    Enter the root directory: [/tmp]:
    Enter the user directory: [sundaram]:
    Enter the purpose of the directory: stock-checker
    Created output directory '/tmp/sundaram/stock-checker/2024-01-02-213509'


delete-old-files
----------------

This script will delete all old files belonging to the current or specified username in the /tmp or specified directory.

jsonl2json
----------

This script will parse a JSONL file and write a JSON file for each line in the JSONL file.

profile-data-file
-----------------

This script will output the following attributes of a specified file:
- date created
- md5sum
- line count
- byte size
  
Sample invocation:


.. code-block:: shell

    profile-data-file requirements.txt
    File: /home/sundaram/projects/data-file-utils/requirements.txt
    md5sum: 2063352be9cbfa5bd1f1425524dbb77b
    create_date: 2023-12-18 11:35:54.242520
    byte_size: 14
    line_count: 2


tsv2json
--------

This script will parse a tab-delimited file and write a JSON file.


xlsx2tsv
--------

This script will parse an Excel file and write a tab-delimited file for each worksheet.

Sample invocation:


.. code-block:: shell

    xlsx2tsv --infile ~/projects/experiments/xlsx2tsv/genetics.xlsx
    --config_file was not specified and therefore was set to '/home/sundaram/projects/experiments/xlsx2tsv/venv/lib/python3.10/site-packages/data_file_utils/conf/config.yaml'
    --outdir was not specified and therefore was set to '/tmp/xlsx2tsv/2023-12-22-142224'
    Created output directory '/tmp/xlsx2tsv/2023-12-22-142224'
    --logfile was not specified and therefore was set to '/tmp/xlsx2tsv/2023-12-22-142224/xlsx2tsv.log'
    Sheet 'genes' has been written to '/tmp/xlsx2tsv/2023-12-22-142224/genes.tsv
    Sheet 'transcripts' has been written to '/tmp/xlsx2tsv/2023-12-22-142224/transcripts.tsv'
    Sheet 'proteins' has been written to '/tmp/xlsx2tsv/2023-12-22-142224/proteins.tsv'
    The log file is '/tmp/xlsx2tsv/2023-12-22-142224/xlsx2tsv.log'
    Execution of '/home/sundaram/projects/experiments/xlsx2tsv/venv/lib/python3.10/site-packages/data_file_utils/xlsx2tsv.py' completed
