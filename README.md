# Nagios Check Rubrik: check_rubrik

## Overview

This is a simple Nagios check script to monitor your Rubrik Physical or Virtual appliance

## Usage

Check Rubrik Edge (Virtual appliance) or Brik (Physical appliance).
The scripts has 4 checks available:
- node - check node statusn"
- runway - check runway availablen"
- storage - shows percent availablen"
- tasks - check status of the tasks"



### Install in Nagios

Edit your commands.cfg and add the following

<pre><code>
define command {
        command_name                 check_rubrik_node             
        command_line                  $USER1$/check_rubrik -H $HOSTADDRESS$ -f /etc/nagios/adagios/authDir/authFileRubrik.txt -l node
}

define command {
        command_name                  check_rubrik_runaway
        command_line                  $USER1$/check_rubrik -H $HOSTADDRESS$ -f /etc/nagios/adagios/authDir/authFileRubrik.txt -l runaway
}

define command {
         command_name                   check_rubrik_storage          
        command_line                  $USER1$/check_rubrik -H $HOSTADDRESS$ -f /etc/nagios/adagios/authDir/authFileRubrik.txt -l storage -w 20 -c 10
}

define command {
         command_name                   check_rubrik_tasks            
        command_line                  $USER1$/check_rubrik -H $HOSTADDRESS$ -f /etc/nagios/adagios/authDir/authFileRubrik.txt -l tasks -c 1
}

define command {

</code></pre>


