# Schema and Mapping
## Full Schema

The **Subject** entity is the outer most record in the CDA schema. Within the **Subject** record are the fields for the **Subject** (demographic and other subject-specific information) as well as the record of all **ResearchSubject** and **File** records associated with that **Subject**. Each **ResearchSubject** record has fields associated with the **ResearchSubject**, as well as records for the **Diagnosis** and **Specimen** entities associated with that **ResearchSubject**, and so on.
 

| [Subject](#subject) |                                             |                              |                               |                            |
| ------- | ------------------------------------------- | ---------------------------- | ----------------------------- | -------------------------- |
|         | id                                          |                              |                               |                            |
|         | identifier.system                           |                              |                               |                            |
|         | identifier.value                            |                              |                               |                            |
|         | species                                     |                              |                               |                            |
|         | sex                                         |                              |                               |                            |
|         | race                                        |                              |                               |                            |
|         | ethnicity                                   |                              |                               |                            |
|         | days\_to\_birth                             |                              |                               |                            |
|         | subject\_associated\_project                |                              |                               |                            |
|         | **[File](#file):**                          |                              |                               |                            |
|         |                                             | id                           |                               |                            |
|         |                                             | identifier.system            |                               |                            |
|         |                                             | identifier.value             |                               |                            |
|         |                                             | label                        |                               |                            |
|         |                                             | data\_category               |                               |                            |
|         |                                             | data\_type                   |                               |                            |
|         |                                             | file\_format                 |                               |                            |
|         |                                             | associated\_project          |                               |                            |
|         |                                             | drs\_uri                     |                               |                            |
|         |                                             | byte\_size                   |                               |                            |
|         |                                             | checksum                     |                               |                            |
|         | **[ResearchSubject](#researchsubject):**    |                              |                               |                            |
|         |                                             | id                           |                               |                            |
|         |                                             | identifier.system            |                               |                            |
|         |                                             | identifier.value             |                               |                            |
|         |                                             | primary\_disease\_type       |                               |                            |
|         |                                             | primary\_disease\_site       |                               |                            |
|         |                                             | associated\_project          |                               |                            |
|         |                                             | **[Diagnosis](#diagnosis):** |                               |                            |
|         |                                             |                              | id                            |                            |
|         |                                             |                              | identifier.system             |                            |
|         |                                             |                              | identifier.value              |                            |
|         |                                             |                              | primary\_diagnosis            |                            |
|         |                                             |                              | age\_at\_diagnosis            |                            |
|         |                                             |                              | morphology                    |                            |
|         |                                             |                              | stage                         |                            |
|         |                                             |                              | grade                         |                            |
|         |                                             |                              | **[Treatment](#treatment):**  |                            |
|         |                                             |                              |                               | id                         |
|         |                                             |                              |                               | identifier.system          |
|         |                                             |                              |                               | identifier.value           |
|         |                                             |                              |                               | treatment\_type            |
|         |                                             |                              |                               | treatment\_outcome         |
|         |                                             |                              |                               | days\_to\_treatment\_start |
|         |                                             |                              |                               | days\_to\_treatment\_end   |
|         |                                             | **[File](#file):**           |                               |                            |
|         |                                             |                              | id                            |                            |
|         |                                             |                              | identifier.system             |                            |
|         |                                             |                              | identifier.value              |                            |
|         |                                             |                              | label                         |                            |
|         |                                             |                              | data\_category                |                            |
|         |                                             |                              | data\_type                    |                            |
|         |                                             |                              | file\_format                  |                            |
|         |                                             |                              | associated\_project           |                            |
|         |                                             |                              | drs\_uri                      |                            |
|         |                                             |                              | byte\_size                    |                            |
|         |                                             |                              | checksum                      |                            |
|         |                                             | **[Specimen](#specimen):**   |                               |                            |
|         |                                             |                              | id                            |                            |
|         |                                             |                              | identifier.system             |                            |
|         |                                             |                              | identifier.value              |                            |
|         |                                             |                              | associated\_project           |                            |
|         |                                             |                              | age\_at\_collection           |                            |
|         |                                             |                              | primary\_disease\_type        |                            |
|         |                                             |                              | anatomical\_site              |                            |
|         |                                             |                              | source\_material\_type        |                            |
|         |                                             |                              | specimen\_type                |                            |
|         |                                             |                              | derived\_from\_specimen       |                            |
|         |                                             |                              | derived\_from\_subject        |                            |
|         |                                             |                              | **[File](#file):**            |                            |
|         |                                             |                              |                               | id                         |
|         |                                             |                              |                               | identifier.system          |
|         |                                             |                              |                               | identifier.value           |
|         |                                             |                              |                               | label                      |
|         |                                             |                              |                               | data\_category             |
|         |                                             |                              |                               | data\_type                 |
|         |                                             |                              |                               | file\_format               |
|         |                                             |                              |                               | associated\_project        |
|         |                                             |                              |                               | drs\_uri                   |
|         |                                             |                              |                               | byte\_size                 |
|         |                                             |                              |                               | checksum                   |


## Subject
| Common Data Format (present in CDA) | GDC field name                                                         | PDC field name                     | IDC field name                   |
| ----------------------------------- | ---------------------------------------------------------------------- | ---------------------------------- | -------------------------------- |
| id                                  | case.submitter\_id                                                     | cases.case\_submitter\_id          | files.PatientID                  |
| identifier.system                   | GDC                                                                    | PDC                                | IDC                              |
| identifier.value                    | case.submitter\_id                                                     | cases.case\_submitter\_id          | files.PatientID                  |
| species                             | Homo sapiens                                                           | cases.taxon                        | files.tcia\_species              |
| sex                                 | case.demographic.gender                                                | cases.demographics.gender          | No available mapping             |
| race                                | case.demographic.race                                                  | cases.demographics.race            | No available mapping             |
| ethnicity                           | case.demographic.ethnicity                                             | cases.demographics.ethnicity       | No available mapping             |
| days\_to\_birth                     | case.demographic.days\_to\_birth                                       | cases.demographics.days\_to\_birth | No available mapping             |
| subject\_associated\_project        | Create array of all projects for all ResearchSubjects for this Subject |                                    | files.collection\_id             |
|                                     |                                                                        |                                    |                                  |
| [ResearchSubject](#researchsubject) |                                                                        |                                    | No ResearchSubject entity in IDC |
| [File](#file)                       |                                                                        |                                    |

## ResearchSubject
| Common Data Format (present in CDA) | GDC field name             | PDC field name               | IDC field name |
| ----------------------------------- | -------------------------- | ---------------------------- | -------------- |
| id                                  | cases.case\_id             | cases.case\_id               | Not Applicable |
| identifier.system                   | GDC                        | PDC                          |                |
| identifier.value                    | cases.case\_id             | cases.case\_id               |                |
| primary\_disease\_type              | cases.disease\_type        | cases.disease\_type          |                |
| primary\_disease\_site              | cases.primary\_site        | cases.primary\_site          |                |
| associated\_project                 | cases.project.project\_id  | cases.project\_submitter\_id |                |
|                                     |                            |                              |                |
| [Diagnosis](#diagnosis)             |                            |                              |                |
| [Specimen](#specimen)               |                            |                              |                |
| [File](#file)                       |                            |                              |                |

## Diagnosis
| Common Data Format (present in CDA) | GDC field name                     | PDC field name                     | IDC field name |
| ----------------------------------- | ---------------------------------- | ---------------------------------- | -------------- |
| id                                  | cases.diagnoses.diagnosis\_id      | cases.diagnoses.diagnosis\_id      | Not applicable |
| identifier.system                   | GDC                                | PDC                                |                |
| identifier.value                    | cases.diagnoses.diagnosis\_id      | cases.diagnoses.diagnosis\_id      |                |
| primary\_diagnosis                  | cases.diagnoses.primary\_diagnosis | cases.diagnoses.primary\_diagnosis |                |
| age\_at\_diagnosis                  | cases.diagnoses.age\_at\_diagnosis | cases.diagnoses.age\_at\_diagnosis |                |
| morphology                          | cases.diagnoses.morphology         | cases.diagnoses.morphology         |                |
| grade                               | cases.diagnoses.tumor\_grade       | cases.diagnoses.tumor\_grade       |                |
| stage                               | cases.diagnoses.tumor\_stage       | cases.diagnoses.tumor\_stage       |                |
|                                     |                                    |                                    |                |
| [Treatment](#treatment)             |                                    |                                    |                |

## Treatment
| Common Data Format (present in CDA) | GDC field name                                 | PDC field name                                        | IDC field name |
| ----------------------------------- | ---------------------------------------------- | ----------------------------------------------------- | -------------- |
| id                                  | cases.diagnoses.treatments.treatment\_id       | cases.diagnoses.treatments.treatment\_id              | Not applicable |
| identifier.system                   | GDC                                            | PDC                                                   |                |
| identifier.value                    | cases.diagnoses.treatments.treatment\_id       | cases.diagnoses.treatments.treatment\_id              |                |
| treatment\_type                     | cases.diagnoses.treatments.treatment\_type     | cases.diagnoses.treatments.treatment\_type            |                |
| treatment\_outcome                  | cases.diagnoses.treatments.treatment\_outcome  | cases.diagnoses.treatments. treatment\_outcome        |                |
| days\_to\_treatment\_start          | cases.diagnoses.treatments.days\_to\_treatment | cases.diagnoses.treatments.days\_to\_treatment\_start |                |
| days\_to\_treatment\_end            |                                                | cases.diagnoses.treatments.days\_to\_treatment\_end   |                |

## Specimen
| Common Data Format (present in CDA) | GDC field name                                       | PDC field name                            | IDC field name |
| ----------------------------------- | ---------------------------------------------------- | ----------------------------------------- | -------------- |
| id                                  | cases.samples.sample\_id                             | cases.samples.sample\_id                  | Not applicable |
|                                     | cases.samples.portions.portion\_id                   | cases.samples.aliquots.aliquot\_id        |                |
|                                     | cases.samples.portions.slide\_id                     |                                           |                |
|                                     | cases.samples.portions.analytes.analyte\_id          |                                           |                |
|                                     | cases.samples.portions.analytes.aliquots.aliquot\_id |                                           |                |
| identifier.system                   | GDC                                                  | PDC                                       |                |
| identifier.value                    | cases.samples.sample\_id                             | cases.samples.sample\_id                  |                |
|                                     | cases.samples.portions.portion\_id                   | cases.samples.aliquots.aliquot\_id        |                |
|                                     | cases.samples.portions.slide\_id                     |                                           |                |
|                                     | cases.samples.portions.analytes.analyte\_id          |                                           |                |
|                                     | cases.samples.portions.analytes.aliquots.aliquot\_id |                                           |                |
| associated\_project                 | cases.project.project\_id                            | cases.project\_submitter\_id              |                |
| age\_at\_collection                 | cases.demographic.days\_to\_birth                    | cases.demographics.days\_to\_birth        |                |
| derived\_from\_subject              | cases.submitter\_id                                  | cases.case\_submitter\_id                 |                |
| primary\_disease\_type              | cases.disease\_type                                  | cases.disease\_type                       |                |
| anatomical\_site                    | cases.samples.biospecimen\_anatomic\_site            | cases.samples.biospecimen\_anatomic\_site |                |
| source\_material\_type              | cases.samples.sample\_type                           | cases.samples.sample\_type                |                |
| specimen\_type                      | sample, portion, slide, analyte, aliquot             | sample, aliquot                           |                |
| derived\_from\_specimen             | cases.samples.sample\_id                             | cases.samples.sample\_id                  |                |
|                                     | cases.samples.portions.portion\_id                   |                                           |                |
|                                     | cases.samples.portions.analytes.analyte\_id          |                                           |                |
| derived\_from\_subject              | cases.submitter\_id                                  | cases.case\_submitter\_id                 |                |
|                                     |                                                      |                                           |                |
| [File](#file)                       |                                                      |                                           |                |

## File
| Common Data Format (present in CDA) | GDC field name                 | PDC field name                 | IDC field name                        |
| ----------------------------------- | ------------------------------ | ------------------------------ | ------------------------------------- |
| id                                  | files.file\_id                 | files.file\_id                 | files.crdc\_instance\_uuid'           |
| identifier.system                   | GDC                            | PDC                            | IDC                                   |
| identifier.value                    | files.file\_id                 | files.file\_id                 | files.crdc\_instance\_uuid'           |
| label                               | files.file\_name               | files.file\_name               | files.gcs\_url                        |
| data\_category                      | files.data\_category           | files.data\_category           | Imaging                               |
| data\_type                          | files.data\_type               | files.file\_type               | files.Modality                        |
| file\_format                        | files.data\_format             | files.file\_format             | DICOM                                 |
| associated\_project                 | cases.project.project\_id      | cases.project\_submitter\_id   | files.collection\_id                  |
| drs\_uri                            | drs://dg.4DFC:{files.file\_id} | drs://dg.4DFC:{files.file\_id} | No DCF formatting currently available |
| byte\_size                          | files.file\_size               | files.file\_size               | No mapping available                  |
| checksum                            | files.md5sum                   | files.md5sum                   | No mapping available                  |
