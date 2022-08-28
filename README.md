# Configuring Helios Server for IT207

  

Hello,

If you have already attempted to access your Helios web server account, you may have experienced a message on the page with the title “Error 403: Forbidden”.

[insert image]

This is not an error you will often see, or you did something wrong. You simply have not configured your Helios server yet. The reason you will see this message is that you are trying to open a webpage that does not exist and by default Helios web server is configured to NOT show you the directory indexes.

To resolve this issue, there is a simple fix if you follow the below instructions. But in short we will be creating a file called `.htaccess` and place it inside the `helios_html` folder. Inside the file we will have 3 lines of code as below;
```
Options +Indexes
Options +Includes
AddHandler server-parsed .html
```

-   Options +Indexes
	-   This enables directory indexes throughout your entire site.
-   Options +Includes
	-   This tells the server that you want to permit files to be parsed for SSI directives
-   AddHandler server-parsed .html
	-   This tells the server that for SSI directives you also want HTML files to be parsed as well, by default this options reserved for ‘.shtml’ files.
    
> Note: You can configure your `.htaccess` file further if you like, but this should allow you to complete this course without any issue.

## Setup Instructions
> Note: For the below instructions I will be using Notepad as my text editor and Filezilla for transferring files to server. You can use any other program alternatives for these tasks.

>Note:  Complete SSH instructions so you know how to access your Helios Web Server.

1. Create a file either on your local machine or on the server and name it `.htaccess`. Make sure this file has no extension. 
2. Once the file is created, open it to edit and insert 3 lines of code described above.
3. Save the file.
4. If you created the file on your local machine, upload it to `Helios Web Server` via FTP and place it inside the `helios_html` folder -  right next to `IT207` folder.
5. Right click the `.htaccess` file on Helios Web Server  and select "File Permissions" at the bottom of the context menu. Verify that both Group and Public permissions are set to allow them to Read. This can be done by either clicking the box next to "Read" or by entering in 644 in the box labeled "Numeric" value.
6. Hard refresh your browser.
7. After these steps, you should not be receiving the same error anymore. 

## Troubleshooting
If you are still getting the error after completing the steps above, make sure you have refreshed your browser window.
If the error persists, make sure your URL is correct, and you are trying to open the correct file that you want it to be open. 
If none of the above helps, please visit your Lab Instructor during office hours.
## Resources

-   [https://help.dreamhost.com/hc/en-us/articles/215747718-Control-directory-indexes-with-an-htaccess-file](https://help.dreamhost.com/hc/en-us/articles/215747718-Control-directory-indexes-with-an-htaccess-file)
    
-   [https://help.dreamhost.com/hc/en-us/articles/215747688-Using-SSI-on-files-with-an-html-extension](https://help.dreamhost.com/hc/en-us/articles/215747688-Using-SSI-on-files-with-an-html-extension)
