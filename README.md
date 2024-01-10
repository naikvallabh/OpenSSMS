# OpenSSMS
Open SQL Server Management Studio with another credential or as another user

Suppose you have been provided with 2 credentials, one is your general windows account (say my windows account name is vnaik@company.com) and another is private account (say Vallabh.Naik@company.com). A enterprise may do this so that with one account you open your personal system (outlook, Teams, Zoom, etc) and a dedicated account to open get access to enterprise servers. Lets say you are permitted to access SSMS only using this dedicated account. In this case you cannot use "windows authenticaion" option to connect SSMS to database neither you can use "SQL Server Authentication" unless the login is expliitely created for your didicated account. 
What we can do in this case is run the SSMS tool with the dedicated account as windows account.
To do this create a .bat file and copy the below command in it (verify the .exe path)
runas /noprofile /netonly /user:company\Vallabh.Naik "C:\Program Files (x86)\Microsoft SQL Server Management Studio 18\Common7\IDE\Ssms.exe"
Next you have to type the password which wont be visible to you, you may not even see the asterics as you type. Click enter and SSMS opens.
you will still see your windows login id on first window and windows authentication selected, but the program will run as for the dedicated account.
