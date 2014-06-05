NBJoomlaAnt
===========

A sample NetBeans 8.0 project for build your joomla extensions on a Joomla 3.x remote website.
The idea is to build a simple development environment for your Joomla 3.x extensions, from where you can go further.

author: Walker Gusmão, walker at praiseweb.com.br. 

# WHAT IT DOES

    * Zips your component into a nbproject/package/projectname.zip file
    * FTPs your components files into the proper directories as long as remote.directory is set properly 
    * (You do that in your project configuration when you specify Remote)

## SHORT PROCESS

    * loads the nbproject/project.properties file
    * loads the private/private.properties file
    * loads the FTP connections file that you specify in the private.properies file
    ** NOTE: You can specify your ${ftp.connections} file directly here.

## REQUERIMENTS

    * You need to have Netbeans Ant Plugin installed, go Tools -> Plugins and install Ant plugin.

## INSTALL INSTRUCTIONS

    1. Git Clone this project on Netbeans, Team -> Git -> Clone, put this url: https://github.com/klarkc/NBJoomlaAnt remeber to enable the "Search for netbeans projects" option.
    2. Right click in your project, go Properties -> Run Configuration, setup your ftp parameters.
    3. In Netbeans 8.0 the RemoteConnections directory is at:
        /home/user/.netbeans/8.0/config/Preferences/org/netbeans/modules/php/project/RemoteConnections
    4. In that directory find the file/connection you are using for your project and put your password on a new line as follows:
        password=XXX123YYY ; where XXX123YYY is your password
        This file must be secured, never add these credentials in your projects.
    5. So you place the following lines into your nbproject/private/private.properties file (this folder is hidden within Netbeans):
        ftp.connections=${netbeans.user}\\config\\Preferences\\org\\netbeans\\modules\\php\\project\\RemoteConnections
        name=projectname
    PS: the projectname is without "com_", or "mod_" or anything else and always lowercase.

## USAGE INSTRUCTIONS

    * First, init your project, creating the needed folders and files. Right Click on the build.xml file, Run Target -> init
    * When you are done, you can build a package: Right Click on the build.xml file, Run Target -> zipup and just install your zip file (nbproject/package/projectname.zip) on any Joomla Website.
    * To update your files directly on the remote website, Right Click on the build.xml file, Run Target -> run-ftp


## HOW ADD FOLDERS AND FILES TO THE FTP PROCESS
    * Add your needed folders and files in run-ftp section of build.xml files, if you need further instructions go ahead: http://ant.apache.org/manual/Tasks/ftp.html