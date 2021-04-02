#Opening Windows PowerShell from searh as (Cntrl+Shift+Enter) will run as adminstrator and C:\WINDOWS\system32> is opened.

ISE: Integrated Scripting Environment

Windows PowerShell uses cmdlets https://superuser.com/questions/1194479/why-are-powershell-commands-named-cmdlets-command-lets-and-what-is-the-differe





>Get-ChildItem 
lists out the items present in pwd 

dir and ls are aliases(nickname) for Get-ChildItem cmdlet

>Get-Alias
Lists out available commands





# PowerShell vs Bash
- output is not returned in a text format but objects

> Get-ChildItem | Select-Object Name 
we are now focusing on single kind of data

> Get-ChildItem | Select-Object -Index 0
first row will be displayed 

> Get-ChildItem | Select-Object -Index 0 | Select_Object Name
Name
----
john

will be displayed. notice there is a header 'Name'


# (Select can also be used instead of Select-Object)




# Mostly we are returned with inforamtion in a tablular format with headers
-we can use paranthese and make the whole cmd as an object
>(Get-ChildItem | Select -First 1).Name
john



# Get-Member 
> Get-ChildItem | Select-Object -Index 0 | Get-Member 

view what properties/methods that object holds 



# Man page for PowerShell
> Get-Help Select-Object

- search for cmdlets surrounding a word
> Get-Help *printer*

> Get-Help network*


# Formatting the output received from a cmd
 - cntrl + Spacebar : lists out available commands 
 
 > Get-ChildItem | Format-Wide

.android                             .AndroidStudio4.0
.atom                                .cache
.config                              .crashlytics
.gradle                              .idlerc
.ipython                             .PyCharmCE2019.1
.PyCharmCE2019.2                     .pylint.d
.tooling                             .VirtualBox
.vscode                              .zenmap
3D Objects                           Cisco Packet Tracer 7.3.0
Contacts                             Desktop
Dev-Cpp                              Documents
Downloads                            Evernote
Favorites                            HP
Links                                Music
OneDrive                             Pictures
Postman                              PycharmProjects
Roaming                              Saved Games
Searches                              source
Videos                               VirtualBox VMs
.bash_history                        .emulator_console_auth_token
.gitconfig                           .node_repl_history
.packettracer                        .pgAdmin4.1057243102.addr
.pgAdmin4.1057243102.log             .pgAdmin4.2123502176.addr
.pgAdmin4.2123502176.log             .pgAdmin4.startup.log


> Get-ChildItem | Format-List
 
Gives extra details about each object 



Name           : .packettracer
Length         : 146
CreationTime   : 08-06-2020 02:06:29
LastWriteTime  : 08-12-2020 15:38:40
LastAccessTime : 02-04-2021 17:59:56
Mode           : -a----
LinkType       :
Target         : {}
VersionInfo    : File:             C:\Users\User\.packettracer
                 InternalName:
                 OriginalFilename:
                 FileVersion:
                 FileDescription:
                 Product:
                 ProductVersion:
                 Debug:            False
                 Patched:          False
                 PreRelease:       False
                 PrivateBuild:     False
                 SpecialBuild:     False
                 Language:



> Get-ChildItem | fl *     # Format Wide
> Get-ChildItem | fl *      #Format List 

# Alias for "Alias" is gal

> gal mv

CommandType     Name                                               Versi
                                                                   on
-----------     ----                                               -----
Alias           mv -> Move-Item 


>gal echo
Write Output



# Pipling with out
1. 
> get-childitem | Out-String

will display the output as String and not as c# object 

2. 
> get-childitem | Out-Null
redirecting to \dev\null 


# Get the output in a text file 

use of > file_name.txt

> get-childitem > direct.txt

type ls to check a "direct.txt" file created


# Reading content from a text file 

> Get-content .\direct.txt

# Reading content from a text file with a particular app

> code .\direct.txt


# GUI view and filtering for a huge chunk of data
> Get-childitem | out-gridview


# PowerShell uses a lot of similar aliases as Unix terminal 
 
>gal mv or gal cp orgal rm

# Copy file to upward directory 

> cp .\direct.txt


# PowerShell categorizes files and folders , both as Items 
