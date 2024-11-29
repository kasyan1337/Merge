# PDF File Merger and Archiver

## Overview

This project is a utility for merging PDF files, organizing them into custom orders, and archiving the input and output files with a structured naming system. The tool is designed for simplicity, ensuring that files remain intact during processing and are archived with appropriate metadata for future reference.

## Features

	•	PDF Merging:
	•	Combine multiple PDF files into a single PDF based on user-specified order.
	•	Ensures only valid PDF files are processed.
	•	Custom File Order:
	•	Displays available PDF files with indices.
	•	Allows the user to specify the order (e.g., 3214 for a specific sequence).
	•	Archiving:
	•	Automatically archives input and output files after processing.
	•	File names in the archive include:
	•	Task number (incremental).
	•	Original file name.
	•	Timestamp of the operation.
	•	Example archive format: 0001 - Application form.pdf - 29.11.2024 - 12:59:34.
	•	Directory Management:
	•	Input files are processed from the input folder.
	•	Merged PDF is saved in the output folder.
	•	Archived files are stored in structured archive/input and archive/output directories.

## Directory Structure
````
project_root/
├── input/            # Place PDF files to be merged here
├── output/           # Stores the merged PDF file
├── archive/
│   ├── input/        # Archived input files
│   ├── output/       # Archived output files
└── main.py           # The main script
````

## Usage

1. Preparing Files

	1.	Place your PDF files in the input folder.
	2.	Ensure the files are valid PDFs.

2. Running the Script

	1.	Execute the script:
````bash
python main.py
````

	2.	If there are files in the output directory, they will be archived automatically before processing new files.

3. Custom File Order

	•	The script lists all files in the input folder and assigns numbers.
	•	Enter the order in which files should be merged (e.g., 3214 for third, second, first, and fourth files in that sequence).

4. Archiving

	•	Once processed, all input and output files are archived with names that include:
	•	Incremental task number.
	•	Original file name.
	•	Timestamp.

Example Workflow

	1.	Place three files in input/:

Application form.pdf
CV.pdf
Motivation letter.pdf


	2.	Run the script:
````bash
python main.py
````

	3.	Enter the order (e.g., 312 for Motivation letter → Application form → CV).
	4.	Result:
	•	Merged file in output/:

Merged_Output.pdf


	•	Archived files:
	•	Input files in archive/input/:

0001 - Application form.pdf - 29.11.2024 - 12:59:34
0001 - CV.pdf - 29.11.2024 - 12:59:34
0001 - Motivation letter.pdf - 29.11.2024 - 12:59:34

	•	Output file in archive/output/:

0001 - Merged_Output.pdf - 29.11.2024 - 12:59:34

Requirements

	•	Python 3.8+
	•	Libraries:
	•	PyPDF2

Install dependencies:
````bash
pip install -r requirements.txt
````

Notes

	•	Ensure all files in input/ are valid PDFs.
	•	Archived files are renamed but retain their original content.
	•	Output files are replaced with each new run, and existing files in output/ are archived before processing.
