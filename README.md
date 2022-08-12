# ICD-
ICD 9 /10 code and CCI 


### Read ICD9/10 Mapping file:
```SAS
Data mapping;
infile '~\ICD9_mapping_ICD10.txt'
                 delimiter='|'
                 missover
                 DSD;
format ICD9_CODE $9. ;
format ICD10_CODE $9. ;
format Code_Description $100. ;
input
                 ICD9_CODE $
                 ICD10_CODE $
                 Code_Description $
     ;
 run;
```
### Read ICD code:
```SAS
PROC IMPORT OUT= WORK.CCI
            DATAFILE= "~\ICD-10.xlsx" 
            DBMS=EXCEL REPLACE;
     GETNAMES=YES;
     MIXED=NO;
     SCANTEXT=YES;
     USEDATE=YES;
     SCANTIME=YES;
RUN;
```
### Read ICD code with CCI weights:
```SAS
PROC IMPORT OUT= WORK.CCI
            DATAFILE= "~\ICD10_withCCI.xlsx" 
            DBMS=EXCEL REPLACE;
     GETNAMES=YES;
     MIXED=NO;
     SCANTEXT=YES;
     USEDATE=YES;
     SCANTIME=YES;
RUN;
```
