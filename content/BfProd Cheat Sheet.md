# **BfProd Cheat Sheet**

Use this cheat sheet when working in BfProd. The cheat sheet covers these areas:

- Macro Express macro
- Using the Macro Express macro to import and existing MARC bibliographic record from Voyager into Marva Quartz
- Editing the description in Marva Quartz  
- Using the Macro Express macro to generate a converted MARC record from the BIBFRAME description in Marva Quartz
- Reviewing the converted MARC record in Voyager and making any changes to the record
- Saving the converted MARC bibliographic record by merging it with the existing MARC bibliographic record 

## **Macro Express macro**

To import the macro, [follow these instructions](<MacroExpress Macro.md>).

## **Using the Macro Express macro to import and existing MARC bibliographic record from Voyager into Marva Quartz**

[Marva Quartz](https://editor.id.loc.gov/bfe2/quartz/) is the latest version of Marva. [Marva Quartz](https://editor.id.loc.gov/bfe2/quartz/) will be used in BfProd. 

- Start in Voyager Cataloging Client
- Find a MARC bibliographic record that you want to update or edit in [Marva Quartz](https://editor.id.loc.gov/bfe2/quartz/)
- Activate the Macro Express macro (Alt+Shift+O) to load the MARC bibliographic record to Marva Quartz

## **Editing the description in Marva Quartz**

- Complete any updates or edits to the description in Marva Quartz
- Save the updated description and post it to BFDB

## **Using the Macro Express macro to generate a converted MARC record from the BIBFRAME description in Marva Quartz**

- Activate the Macro Express macro (Alt+Shift+M) to convert the updated BIBFRAME description in Marva Quartz to MARC and generate a new bibliographic record in Voyager

## **Reviewing the converted MARC record in Voyager and making any changes to the record**

- The converted record is a *new* MARC bibliographic record
- Compare this MARC bibliographic record [before conversion](../images/Bf2MARC-Voyager-Before.jpg) with this copy [after conversion](../images/Bf2MARC-Voyager-After.jpg)
- The converted record will not have local data (906, 925, or 955 fields)
- The original MARC bibliograhpic record is a separate record at this point
- Review the converted MARC bibliographic record to assure that it conforms to the agreed-upon standards for converted MARC bibliographic records (these standards are still in development so please exercise flexibility)

## **Saving the converted MARC bibliographic record by merging it with the existing MARC bibliographic record**

- Save (Boat) the converted MARC bibliographic record
- Evaluate the results in the Voyager Authority Validation pop-up
- When you click on Close on the Voyager Authority Validation pop-up, the [Voyager Bibliographic Dedupe Detection](../images/Bf2MARC-Voyager-LCCNMerge-1.jpg) pop-up will appear
- Click on [Replace/Merge using profile: LCCNmerge](../images/Bf2MARC-Voyager-LCCNMerge-2.jpg)   
- Disregard the pop-up box that says [Error # 75 was generated ...](../images/Bf2MARC-Voyager-LCCNMerge-3.jpg) if it appears (it might not appear) 
- The converted MARC bibliographic record should merge with the existing MARC bibliographic record and there will be a [confirmation pop-up](../images/Bf2MARC-Voyager-LCCNMerge-4.jpg)
- The local data from the 906, 925, and 955 fields of the original MARC bibliograhpic record will appear [at the bottom of the merged record](../images/Bf2MARC-Voyager-LCCNMerge-5.jpg) and the Holdings Record and Item Record from the original MARC bibliographic record will be [brought over to the merged record](../images/Bf2MARC-Voyager-LCCNMerge-5.jpg) 
- Add your cataloger code at the end of the 955 field, using [subfield $a and the text Bf2MARC](../images/Bf2MARC-Voyager-LCCNMerge-6.jpg)
- When you Save (Boat) the record, the local fields will move to the correct location at the [top of the record](../images/Bf2MARC-Voyager-LCCNMerge-7.jpg)
- Run the Voyager Add-on Validator to the record and make [note of the results](../images/Bf2MARC-Voyager-LCCNMerge-8.jpg). This is an area that needs further refinement, but the Add-on Validator results are a good source of feedback to the developers in NDMSO 



