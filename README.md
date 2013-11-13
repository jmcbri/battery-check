# [battery-check](https://github.com/jmcbri/battery-check)

battery-check is a short bash script to check the power (battery) status reported by ACPI (Advanced configuration and Power Interface). If the power level is below a configurable threshold, log the power level and time, and optionally send an email. Not ready for prime time, but I think it works.

## Dependencies

* ACPI (Advanced Configuration and Power Interface)
    - Probably a "sudo apt-get install acpi" away
* awk (gawk) an interpreted language for text processing often used for data extraction and reporting
    - Probably already installed, but if not, "sudo apt-get install gawk"
* send mail capabilities
    - If you don't already have, try [this setup of msmtp](http://www.absolutelytech.com/2010/07/17/howto-configure-msmtp-to-work-with-gmail-on-linux/)
* dc commandline calculator
    - Probably already installed, but if not, you can find it in xxx package    

## Quick start

* Download the source: git clone https://github.com/jmcbri/battery-check
* Open and edit the battery-check file to match your needs. Specifically, the top has configuration information, and you'll need also to decide whether to have the email address embedded in the file or in a seperate file. (See comments in file)
* Save the file somewhere
* Since we are going to have it run as a system cron job, maybe change ownership to root (sudo chown root:root /path/to/file/battery-check)
* Set the file as executable only by root(chmod 700 /path/to/file/battery-check)
* Add the checking as a cron job  
    Add lines to your cron file (there's lots of tutorials, but they're too complicated)  
    sudo gedit /etc/crontab  
    \*/5 \* \* \* \* root /home/jim/bin/battery-check/battery-check

    Make sure there's a return (CRLF at the end)

## Bugs and feature requests

[Please open a new issues](https://github.com/jmcbri/battery-check/issues). Before opening an issue, please search existing issues.

## Copyright and license

Copyright 2013 James J. McBride, GPL 2
