# ICD-
ICD 9 /10 code and CCI 

Convert ICD9 to ICD10:
Read file:
'''
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
'''
