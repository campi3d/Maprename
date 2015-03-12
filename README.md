# Maprename
Copyright (c) 2012 Jens Kafitz

##Description:

Maprename is a small free perl script that will take care of the 
different naming conventions between Mari, Zbrush/Maya and Mudbox. 
You can convert quickly and easily between them in all directions and 
regardless of the number of tiles, no matter if you have 10 or 10.000.
The script renames based on the contents of a folder. 
Individual File Renaming is not supported.

##Install:

Linux:
Before running the script you should run the command 
"chmod +x maprename" in the folder where you placed the script. 
This will make sure the script has the correct permissions. 
Other than that no further setup is required although I would suggest
 setting up an alias for it to be able to run it from any folder.
 
Windows
Perl is not native to Windows therefore you will need to install it. 
The latest installer files can be found here::

http://www.activestate.com/activeperl/downloads

After that no further steps are required, however depending on your 
user rights you might have to give the script read/write access 
by right-clicking on it and setting the properties.


##Usage:

In your terminal or dos command prompt write
 
perl maprename
-s [sourcefolder] [sourceconvention] [targetconvention] -nn [newname] -u -c -p


Sample:
perl maprename -s c:\Textures\ mari zb -nn dispFine -u -c -p
 

##Flags:

-s [sourcefolder]

-s will tell the script which folder your files are in. If the flag is not used the script will run on the current folder you are in.
 
Sample: perl maprename -s c:\Textures\ForRenaming\
 
----------------------------------------

[sourceconvention]	

Will tell the script which naming convention your files are currently in. Supported names are
mari, zb, zbrush, mb, mudbox
 
Mari files need to have their UDIM Number in one of the following formats
 
$Channelname.$UDIM.ext
$Channelname_$UDIM.ext
 
Mudbox and Zbrush Files need to have their files in the following (default) format
 
filename_u$_v$.ext
 
----------------------------------------

[targetconvention]
                    	
Will tell the script which naming convention your files are supposed to change into. Supported names are
 
mari, zb, zbrush, mb, mudbox

----------------------------------------

-nn [newname]	 	
This will allow you to replace the original Channelname with a new one. 

----------------------------------------
 
-u	 	
When converting  into Mudbox/Zbrush excess underscores are stripped out by default to be compliant with Mudbox's Naming Convention. When -u is set, this will be ignored.
 
----------------------------------------

-c	 	
By default your files are simply renamed. When -c is set, your files will be copied into an automatically created subfolder with the name of your targetconvention and renamed there.
 
----------------------------------------

-p	 	
Will give you a before/after preview of the naming. No files will be actually renamed.