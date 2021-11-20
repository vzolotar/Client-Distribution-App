# Client Distribution Application 


### 📝 Description 
This is a simple Client Distribution App which is used to distribute the Application Client software and the related components: Client Application, PowerBuilder libraries, Crystal Reports, PowerBuilder runtime libraries, Security and RF components.  

-----

##### Tools / Languages  
<img src="https://img.shields.io/badge/PowerBuilder-40B5A4?logo=powerbuilder&logoColor=white" /> <img height="20" src="https://img.shields.io/badge/DOS Batch-000000?logo=dos&logoColor=white" />  

##### Platform 
<img height="20" src="https://img.shields.io/badge/Windows-0078D6?logo=windows&logoColor=white" /> 


-----

### ✔️ Usage

### 1️⃣ Main Window

<img src="https://github.com/vzolotar/Client-Distribution-App/blob/main/images/ClientDestribution1.JPG" >

An example of the PowerScript code used in the "release” button on clicked() event. 

````markdown
Int net
integer li_FileNum, li_filenum1, li_funrun1, li_funrun2, li_num1
blob emp_id_pic
blob  lb_text
string  ls_dbg


Net = MessageBox("Info", "Do you want to update All clients?", &
		Exclamation!, OKCancel!, 2)

IF Net = 1 THEN

/**********/

li_filenum1 = FileOpen("C:\NEWclient\sysbin\NEWrelease.txt", StreamMode!)
FileRead(li_filenum1, lb_text)
ls_dbg = string(lb_text)
ls_filetxt = FromAnsi(lb_text)
FileClose(li_filenum1)


li_FileNum = FileOpen( &
		"C:\NEWclient\sysbin\NEWrelease.bat", &
			StreamMode!, Write!, Shared!, Replace!)

FileWrite(li_FileNum, ls_filetxt)

FileClose(li_FileNum)

li_funrun1 = Run("C:\NEWclient\sysbin\NEWrelease.bat", Minimized!)

/**********/


st_6.Text = "All clients were updated."

ELSE

st_6.Text = "Ready for update."
END IF
````



### 2️⃣ Login Window

The login window is used in order to activate the “release” buttons as they are disabled by default. 

<img src="https://github.com/vzolotar/Client-Distribution-App/blob/main/images/ClientDestribution2.JPG" >
