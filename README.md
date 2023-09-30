# QR-code-Attendance-System
By filling the google form students will get a unique QR code in their email and after scanning that they will be able to mark their attendance.

This process contains 3 files,

1) Google form ( which is to be sent to participant for taking their details like name, emailid, phone number, address, etc... ) [Emailid is mandatory]
2) Another google form This google form will contain only 2 fields: emailid and name. This google form is only used to create a prefilled link for attendence. In attendance sheet the details shown will be of this form.
3) Spreadsheet (after creating google form make sure you create a spreadsheet and have the same spreadsheets for both the forms)
   
Procedure:

-> Create a google form and add a blank spreadsheet. Make sure the google form has the fields of required details of participants.

-> Add two more columns in spreadsheet: URL and qrcodeImage.

-> Create another google form with only name field. In settings, make it limit to 1 response. Get a prefilled link and add name of the first entry & submit it.

![1](https://github.com/Devanshi-J-28/QR-code-Attendance-System/assets/135025217/48fa4d4c-ba1b-4ae7-a67c-5cfbe462a0b0)


-> In the field URL, for the first entry add the below formula to cell: =ArrayFormula(if(B2:B="",,"https://docs.google.com/forms/d/e/1FAIpQLSd0tka1HzQtaUKDJTUj3a7zouIs2fq64qVKqOoRYtfPa5uqJA/formResponse?entry.13831516="&encodeurl(B2:B)))
Set your respective link in the above formula. In your original formula it will be viewResponse change it to formResponse and after question mark delete the repective part as referred in the formula.
Column B has all the email addresses. If you have emailids in different column, change B to the respective letter according to your spreadsheet.

![2](https://github.com/Devanshi-J-28/QR-code-Attendance-System/assets/135025217/ffda0f07-7f00-44a4-8673-06d15e68f4b8)

-> For QR column add the below formula to the cell of first entry: =ArrayFormula(if(C2:C="",,image("https://chart.googleapis.com/chart?cht=qr&chs=150x150&chl="&F2:F)))
Column F has all the URLS. Column C is the column having name of all participants. If you have these things in different column, change it accordingly.

![3](https://github.com/Devanshi-J-28/QR-code-Attendance-System/assets/135025217/6ef870d4-a4bb-4589-b900-953ed17d3d2f)

-> After this , In spreadsheet, go to extensions. Extensions will be on the top, it is also visible in the screenshot attached above. In extensions go to apps script.

-> In AppsScript, paste the java script code in code section from the attached javascript file. Make changes according to your spreadsheet. Save and run the code.

-> Then Set the trigger to onFormSubmit in trigger section of AppsScript.


