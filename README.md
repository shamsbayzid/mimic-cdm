# MIMIC-CDM
[OMOP CDM](http://omop.org/CDM) conversion of [MIMIC II clinical demo dataset](http://physionet.org/mimic2/demo/).  This is a PostgreSQL-based implementation of the ETL specification designed to generate CDM v5-compatible CSV files.

>  **This implementation is under active development and is not at all ready to be used for general purpose.** We have made this public so that people can contribute to this effort. We have uploaded the SQL queries, and we appreciate your suggestion to improve the ETL implementation.

## Mapping
Here we list the MIMIC II source tables that have been used to generate OMOP CDM v.5 target tables.

| OMOP CDM Target Table     | MIMIC II Source Tables 
| --------|---------
| person  | d_patients
| death | d_patients 
| condition_occurrence | icd9
| visit_occurrence | icustay_days
| observation_period | icustay_days
| procedure_occurrence | procedureevents, d_codeditems
| drug_exposure | medevents, d_meditems
| measurement | d_labitems, labevents
| note | noteevents
| provider | d_caregivers


**Source code terminologies**

* Condition: ICD-9
* Measurement: LOINC
* Procedure: ICD9-CM procedure codes

> We are using [concept 0 shortcut]( http://www.ohdsi.org/web/hermes/#/concept/0) for now, where 0 means unmapped concept. We will update the concept_ids later. Also note that there are some large tables (for example, measurement), for which we have uploaded a subset of the data (the first 1000 rows).

### Contact
If you have any question or suggestion, please contact [Md Shamsuzzoha Bayzid](https://www.cs.utexas.edu/~bayzid/) at shams.bayzid@gmail.com.

> Written with [StackEdit](https://stackedit.io/).
