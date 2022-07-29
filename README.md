OpenCATS is a Free and Open Source Candidate/Applicant Tracking System designed for Recruiters to manage recruiting process from job posting, candidate application, through to candidate selection and submission.

I have enabled a new role in the opencats application who can manage only the candidate profiles. In this the new role will have only limited access to the components. For ex. it can access the candidates components like adding candidates, searching candidates but cannot access the job orders.
To implement this - 
Insert a new user using sql query in the database. In the category column give it a name (say recruiter).
In config.php I had created a category according to our requirement that we will give to the guest user in the database.
Code of that category - 
'recruiter' => array(
        'candidates' => ACCESS_LEVEL_DELETE,
        'joborders' => ACCESS_LEVEL_DISABLED,
        'companies' => ACCESS_LEVEL_DISABLED,
        'calendar' => ACCESS_LEVEL_DISABLED,
        'reports' => ACCESS_LEVEL_DISABLED,
        'contacts' => ACCESS_LEVEL_DISABLED,
        'lists' => ACCESS_LEVEL_DISABLED,
        'settings' => ACCESS_LEVEL_DISABLED,
),


Another task done is - 
It was not able to read the resumes in pdf format, so it contains solving the bug of parsing files in pdf format.
In php.ini file I have declared class COM
Changes done in php.ini file -
[PHP_COM_DOTNET]
extension=php_com_dotnet.dll
[COM]
com.typelib_file = php_com_dotnet.dll
com.allow_dcom = true
com.autoregister_typelib = true
For parsing of the pdf file I have downloaded the pdftotext.exe file and the next task was to set its path in the config.php file.
