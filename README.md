# PDFAndReact
The App will supposedly write given data on a PDF

## Final Solution
PDF-lib worked perfectly with minor inconvenience. 

## PDF-Lib 
Pdf-lib is nearly perfect libirary but its getFiled 
functions are not picking up any fields from the given pdf
And that is because of different filed names, you can display
All the filed names form.getFieds().find/filter/map(x=>console.log(x.name))
And with those names you can start filling your fields
or you fill the form fields with there own names to make indentification easier.

~~~
 form.getFields().find(x=>{
        // to fields with specific names
        if(x.getName().includes(findAndPrintOnConsole)){
          console.log(x.getName())
        }
       
          try{
            if(typeof form.getField(x.getName()).check === 'function'){
              form.getCheckBox(x.getName()).check()
            }else if(buttons.includes(x.getName())){
              form.getButton(x.getName())
            }else{
              const length = form.getTextField(x.getName()).getMaxLength()
              // fields with max length limit get filled with sliced name
              if(length === undefined || length > 4){
                form.getTextField(x.getName()).setText(x.getName())
              }else{
                form.getTextField(x.getName()).setText(x.getName().slice(0, length))
              }
            }
  
          }catch(err){
            console.log("LOOP ERROR")
            console.log(err)
          }
      
      })
~~~

## CheckChildBox
You can check a child box by giving the function an array of all 
the fields checkboxes and the box number, first box as 1.

## CheckChildBoxes
Contains different functions for different checkboxes, such as 
1 function for yes or no and 1 for gender male and female

## checkCheckBox
takes in the field name from the defined dictionary and the check 
value.

## setDate
takes in form, fieldname from the defined dictionary and date.

## setFromAndToDate
takes in form, fieldname from the dict, from date
and To date

## setPatientAndInsuredData

### setPatientData
Takes the data for patient (upper left side of the form) and fills the fields that are given

### setInsuredData
Takes the data for insured (upper right side of the form) and 
fills the fields that are given

## setInsuranceHeaders
Takes 4 insurance Headers NAME, Address, Address2, city/State/zip

## pdfform.js
pdfform is potentional solution which might pick up the fields
but it is not available on node package instullar or npm 
