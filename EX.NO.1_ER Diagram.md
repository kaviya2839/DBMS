# EXP NO 1: ER DIAGRAM CREATION, RELATIONAL MODEL AND SCHEMA GENERATION  
### DATE
## AIM:
<div align="justify">
   To create a ER Diagram for Bank management system or College management system using ERD Plus tool and generate the relational model with schema. 
</div>

## Algorithm
1. Create a login with https://erdplus.com.
2. Create a new ER Diagram with name
3. Create a strong entity, relation and attributes.
4. Create a weak entity, relation and attributes.
5. Specify attributes unique, multivalued and composite attributes.

### ER Diagram 
![image](https://github.com/prithviraj5703/DBMS/assets/121418418/8a829b03-57c8-4d2b-a743-183a17360cc9)


### Relational model

![image](https://github.com/prithviraj5703/DBMS/assets/121418418/b946fd13-de53-4833-9ef9-5e7e49e6f634)

### SQL DDL Schema 
```python
```CREATE TABLE DOCTOR
(
  DOC-ID INT NOT NULL,
  QUALIFICATION INT NOT NULL,
  SALARY INT NOT NULL,
  PRIMARY KEY (DOC-ID)
);
CREATE TABLE MED_RECORD
(
  PROBLEM INT NOT NULL,
  DATE_OF_EXAMINATION INT NOT NULL,
  REC-ID INT NOT NULL,
  PRIMARY KEY (REC-ID)
);

CREATE TABLE DOCTOR_DNAME
(
  DNAME INT NOT NULL,
  DOC-ID INT NOT NULL,
  PRIMARY KEY (DNAME, DOC-ID),
  FOREIGN KEY (DOC-ID) REFERENCES DOCTOR(DOC-ID)
);

```CREATE TABLE PATIENT
(
  PAT-ID INT NOT NULL,
  PDIAGNOSIS INT NOT NULL,
  PADDRESS INT NOT NULL,
  REC-ID INT NOT NULL,
  PRIMARY KEY (PAT-ID),
  FOREIGN KEY (REC-ID) REFERENCES MED_RECORD(REC-ID)
);
CREATE TABLE PATIENT_PNAME
(
  PNAME INT NOT NULL,
  PAT-ID INT NOT NULL,
  PRIMARY KEY (PNAME, PAT-ID),
  FOREIGN KEY (PAT-ID) REFERENCES PATIENT(PAT-ID)
);

CREATE TABLE HOSPITAL
(
  HOSP-ID INT NOT NULL,
  HOS-NAME INT NOT NULL,
  HADDRESS INT NOT NULL,
  HCITY INT NOT NULL,
  PAT-ID INT NOT NULL,
  DOC-ID INT NOT NULL,
  PRIMARY KEY (HOSP-ID),
  FOREIGN KEY (PAT-ID) REFERENCES PATIENT(PAT-ID),
  FOREIGN KEY (DOC-ID) REFERENCES DOCTOR(DOC-ID)
);
```
## RESULT 
<div align="justify">
Thus the ER diagram was drawn and relational diagram, SQL DDL staements are generated using ERD plus tool.
</div>
