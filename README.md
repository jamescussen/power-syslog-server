﻿Power Syslog Server
===================

            



![Image](https://github.com/jamescussen/power-syslog-server/raw/master/powersyslog2.0_400x400.png)

**Version 1.0 Features:**



  *  Zero installation. 
  *  Signed Powershell Script. 
  *  Real time log display (Approximately 1000 lines). 
  *  Copy the displayed text with the Copy Text button. This is useful for more in depth analysis in your favourite notepad software.

  *  Rolling log files based on file size and number of files to keep. 
  *  Clear display and Pause display functions. 
  *  Filter real-time display logging with regular expression. 
  *  Filter logging to file with regular expression. 
  *  Open firewall for Syslog Server port with the click of a button. If you are not seeing any syslog output in the Power Syslog Server display log then try pressing the Open Firewall button.

  *  Server listening port can be changed by creating a config file (PowerSyslogServerSettings.cfg) in the same directory as the script. The config file needs to have text in it in the following format 'SysLogPort=514'. This allows you to maintain the integrity
 of the code signing by not directly editing the script file. 
**Version 2.0 features:**


  *  Added output formatting options to work with Sonus LX tool and AudioCodes Syslog Viewer tool (Commonly used Skype for Business syslog tools used with SBC devices).

  *  In version 2 if you create a config file named 'PowerSyslogServerSettings.cfg' in the same directory as the tool it will use the config file to save all of its settings. The SyslogPort='514' setting remains a hidden setting that can still be used in the
 config file to change the listening port number. 
  *  UDP socket code has been made more robust to deal with errors when the listening port is being used by another app.

  *  Changed the font to Courier New for fixed width goodness. 
  *  Fixed issue with rolling files in folders including '.' in name and faster processing.


**2.01 Bug Fixes (9/8/2017):**





  *  Fixed Sonus LX output formatting to only have LF and not CRLF. 
  *  Increased socket buffer and tuned threading to fix dropped packet issues and double writing of some lines.

  *  Added disable display checkbox to increase performance when display is not required.


 





Version 2.0 of Power Syslog Server now gives you the option to add additional prefix formatting to the start of each line of syslog output. From the research I have done the format of output from each syslog server varies greatly and contains items such
 as date/time, text based priority field interpretation (ie. The <135> value at the start of syslog messages sent on the wire) and IP Address of the server that sent the message.


The reason that these prefixes are important is that if you want to import the file output back into a tool like Sonus LX or AudioCodes Syslog Viewer to generate call flow diagrams or other features the file needs to be in a format that these tools can interpret.
 So in order to achieve this, the Format dropdown box has been added in version 2. The Format setting will alter the outputs into the required format for Sonus LX or AudioCodes syslog tools. In addition to these specific tool formats, some other generic prefix
 formats have been added which will make the output files easier for humans to read.


**Output Formats**






**Format**




**Example Prefix Format**




**Comment**






**None**




Raw output




Output syslog in the exact format that it was sent from the device in.






**AudioCodes**




'17:50:17.588  10.20.2.170     local0.notice'




Output syslog in AudioCodes Syslog Viewer tool format.






**SonusLX**




'10.20.1.150:53434 <==>'




Output syslog in the same format as the Sonus LX tool.






**Level**




'Local0.Debug'




To prefix the syslog with the Facility and Severity levels.






**DateTime**




'2011-10-11 15:00:02.123'




To prefix the syslog with the date and time.






**DateTimeLevel**




'2011-10-11 15:00:02.123 Local0.Debug'




To prefix the syslog with Date/Time and Facility/Severity.






**DateTimeLevelIP**




'2011-10-11 15:00:02.123 Local0.Debug    192.168.0.100'




To prefix the syslog with Date/Time, Facility/Severity, and IP Address of the device.






***Note:*** *Sonus LX tool cannot open AudioCodes files and AudioCodes syslog tool cannot open LX files. This is
 because there are special lines of output generated by each brand of SBC that the specific syslog tools use for generating call flow diagrams. So you need to select the correct format for the device and tool you are using if you want to be able to import the
 files.*


 


**For full information about Power Syslog Server please refer to the following page: [http://www.myteamslab.com/2014/09/power-syslog-server.html](http://www.myteamslab.com/2014/09/power-syslog-server.html)**


 







        
    
