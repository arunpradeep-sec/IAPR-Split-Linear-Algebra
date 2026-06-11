# IAPR File Generator

A simple web-based utility to automatically generate experiment-wise IAPR upload files from CAMU export sheets.

## Features

* Generate separate IAPR files for each experiment.
* Automatically detects the number of experiments from the uploaded marks file.
* Supports Viva marks integration.
* Automatically normalizes experiment marks to 90 and adds Viva marks out of 10.
* Generates all experiment files in a single ZIP download.
* Works entirely in the browser — no data is uploaded to any server.

## Website

https://arunpradeep-sec.github.io/IAPR-Split/

---

## Input Files Required

### 1. Experiment Marks File

Requirements:

* Row 1 must contain headers.
* Student data must start from Row 2.
* Column C must contain the Register Number / ID Number.
* Experiment marks must be present from Columns G onwards.
* Remove the last column containing **"Last downloaded from this course"** before uploading.

### 2. Viva File

Requirements:

* Row 1 must contain headers.
* Student data must start from Row 2.
* Column C must contain the Register Number / ID Number.
* Viva marks for Experiments 1–9 must be present in Columns G to O.
* Remove the last column containing **"Last downloaded from this course"** before uploading.

### 3. Output Template

Requirements:

* Upload any one IAPR template downloaded from CAMU.
* The template must contain the columns:

  * StuRollNo
  * Mark
* Rows 1 and 2 are treated as header rows.
* Data entry starts from Row 3.

---

## Mark Calculation

### Experiments 1–9

Final Mark = (Experiment Mark × 0.9) + Viva Mark

Example:

* Experiment Mark = 80
* Viva Mark = 7

Final Mark = 79

### Experiment 10

Final Mark = Experiment Mark

No Viva marks are added.

---

## Matching Criteria

Student records are matched using:

# Experiment File Column C

# Viva File Column C

Output Template StuRollNo

---

## Handling Missing Data

### Missing Viva Marks

If a student has no Viva mark:

Viva Mark = 0

### Missing Student

If a student is not found:

Mark = 0

---

## Output

The application automatically generates:

* IAPR_Exp01.xlsx
* IAPR_Exp02.xlsx
* IAPR_Exp03.xlsx
* ...
* IAPR_ExpNN.xlsx

and downloads them as:

IAPR_Files.zip

---

## Disclaimer

This tool was developed for educational and academic administrative purposes to simplify IAPR mark preparation and upload.

While every effort has been made to ensure the accuracy of the generated outputs, users are responsible for verifying all results before use.

Errors and Omissions Excepted (E&OE).
