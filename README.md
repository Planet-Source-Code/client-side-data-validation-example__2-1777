<div align="center">

## Client Side Data Validation Example


</div>

### Description

The following example uses javascript to perform client side data validation. When the submit button is pressed the {validate} function executes and checks for data in the USER ID and PASSWORD input objects. If either of these fields are empty then the function returns a false to the form's OnSubmit to prevent posting to the server. It also issues a set focus to the object that data validation failed on. The function also verifies that the password and password confirmation match.

There are two examples of the validate function listed below. The first uses object names to reference the form's objects {preferred}. The second uses the {elements} property to reference the form's objects.

http://www.truegeeks.com/asp/mam/osdoc/osframe.asp
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[N/A](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/empty.md)
**Level**          |Beginner
**User Rating**    |3.5 (14 globes from 4 users)
**Compatibility**  |
**Category**       |[Forms Validation Processing](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/forms-validation-processing__2-76.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/client-side-data-validation-example__2-1777/archive/master.zip)





### Source Code

```
<HTML>
<BODY BGCOLOR=#C3C3C3>
<!--Client Side Validation-->
<SCRIPT LANGUAGE=JAVASCRIPT>
function validate(form) {
//Data validation using object names to reference objects
if (form.USERID.value == "") {
  alert("You must enter a User ID");
  form.USERID.focus()
  return false; }
if (form.PSW.value == "") {
  alert("You must enter a Password");
  form.PSW.focus()
  return false; }
if (form.PSW.value != form.CPSW.value) {
  alert("Password and Password Confirmation Did Not Match");
  form.CPSW.focus()
  return false; }
return true;
}
function validate2(form) {
//Data validation using elements[] to reference objects
if (form.elements[0].value == "") {
  alert("You must enter a User ID");
  form.elements[0].focus()
  return false; }
if (form.elements[1].value == "") {
  alert("You must enter a Password");
  form.elements[1].focus()
  return false; }
if (form.elements[1].value != form.elements[2].value) {
  alert("Password and Password Confirmation Did Not Match");
  form.elements[1].focus()
  return false; }
return true;
}
</SCRIPT>
<FORM onSubmit="return validate(this)" ACTION="http://www.truegeeks.com" METHOD=post>
<TABLE><TR>
<TD ALIGN=right><STRONG><FONT color=#000080>USER ID:</FONT></STRONG></TD>
<TD><INPUT TYPE=TEXTBOX NAME=USERID SIZE=25 MAXLENGTH=25></TD></TR>
<TR>
<TD ALIGN=right><FONT color=#000080><STRONG>PASSWORD:</STRONG></FONT></TD>
<TD><INPUT TYPE=password NAME=PSW SIZE=25 MAXLENGTH=25></TD></TR>
<TR>
<TD ALIGN=right><FONT color=#000080><STRONG>CONFIRM PASSWORD:</STRONG></FONT></TD>
<TD><INPUT TYPE=password NAME=CPSW SIZE=25 MAXLENGTH=25></TD></TR>
<TR><TD><TD><INPUT TYPE=submit VALUE="Submit 1"></TD></TR>
</TABLE></FORM>
</BODY></HTML>
```

