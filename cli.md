`rename`

Rename is use to rename files and folders

`$ rename oldfile newfile` 

If for any reason `rename` does not work try `mv`

`mv`  

mv is used to move files and folders

`$ mv fileOrFolder newLocation`  

mv can also be used to rename files. Just do

`$ mv oldfileName.extension newFileName.extension`

`refreshenv`  
On Windows cmd.exe, you need to restart the command prompt for changes
you made - for example you installed python. I've not tested this on
other versions of Windows but on Windows 10 (from Anniversary Update), 
on the command prompt you can type `c:> refreshenv` and path variables
are updated. It basically does what a restart would do without having to
restart, obviously.
