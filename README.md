# MIMIC-CDM
[OMOP CDM](http://omop.org/CDM) conversion of [MIMIC II clinical demo dataset](http://physionet.org/mimic2/demo/).  This is a PostgreSQL-based implementation of the ETL specification designed to generate CDM v5-compatible CSV files.

>  **This implementation is under active development and is not at all ready to be used for general purpose.** We have made this repository public so that people can contribute to this effort. We have uploaded the SQL queries, and we appreciate your suggestion to improve the ETL implementation.

## Mapping
Here we list the MIMIC II source tables that we have used to generate OMOP CDM v.5 target tables.

| Target Table     | MIMIC II Source Tables 
| --------|---------
| person  | d_patients
| death | d_patients 
| condition_occurrence | icd9
| visit_occurrence | icustay_days
| procedure_occurrence | procedureevents, d_codeditems
| drug_exposure | medevents, d_meditems
| measurement | d_labitems, labevents
| note | noteevents
| provider | d_caregivers


**Source code terminologies**

* Condition: ICD-9
* Measurement: LOINC
* Procedure: ICD9-CM procedure codes

> We are using [concept 0 shortcut]( http://www.ohdsi.org/web/hermes/#/concept/0) for now, where 0 means unmapped concept. We will update the concept_ids later.

### Contact
If you have any question or suggestion, please contact [Md Shamsuzzoha Bayzid](https://www.cs.utexas.edu/~bayzid/) at shams.bayzid@gmail.com.

> Written with [StackEdit](https://stackedit.io/).
