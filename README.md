# Snort-email-alert
Snort will have a file call alert when an alert is generated /var/log/snort/alert.
we want to know the new alert when it is added by email.

1-Use Gmail from Terminal

 *Tap this commands :

sudo apt-get update
sudo apt-get install msmtp-mta
touch /var/log/msmtp.log

*Access to this web site: myaccount.google.com/lesssecureapps
activate the “Less secure app access”
*Open the file and copy the following:

cd ~
nano .msmtprc


*Tap this commands:

chmod 600 .msmtprc
sudo apt-get install heirloom-mailx

*Add the following line to /etc/apt/sources.list

deb http://security.ubuntu.com/ubuntu trusty-security main universe

*Then:

sudo apt-get update

*Open a file:

 nano ~/.mailrc

*Add the following lines:

set sendmail="/usr/bin/msmtp"
set message-sendmail-extra-arguments="-a gmail"

2-Generate email script alert

*create script file :

touch email
touch /var/log/snort/alert1

 3-Generate the script every 5 minutes

*Tap :

	   crontab -e

*file output:

   	*/5 * * * * /path/to/script

