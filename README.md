# AEFI_Vaccine_Analysis

## INTRODUCTION
An adverse event following immunization (AEFI) is any health-related issue that occurs during the intake of vaccine or post the intake. The adverse event is a temporal association without any causal relation to the vaccine intake.

## DATASET AND FEATURES
The VAERS data is verified and checked for reliability by Center of Disease Control and Prevention, the national public health agency of the U.S. The dataset was extracted from VAERS website for a period from December 2020 up to October 2021. Currently, the data was filtered appropriately to extract data associated to COVID-19 since first we want to focus on studying the potential adverse effects of the U.S. licensed COVID-19 vaccines. VAERS data is a set of 3 open-source raw data files.

## DATA PREPARATION
Some key steps of data preparation are highlighted below which acted as a base for the model building.
• Join the 3 datasets based on the VAERS_ID. The volume might increase from the base data as in the VAERSSYMPTOMS file can have multiple records for a single VAERS_ID. This is because, a single patient can have more than 5 symptoms which are inserted as multiple entries.
• Categorical encoding is done on some of the variables like other meds, current illness, disabilities, sex, Vaccine manufacturer.
• Date imputing is done using forward imputing and backward imputing rules as part of the data cleansing step. Records with irrelevant date are dropped. This step is done for Vaccine Intake date and Event Reported date.
• 17 Baseline features have been identified based on the medical history column and they are encoded using dummies.
• Records which are outliers for NUMDAYS are removed.
