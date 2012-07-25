logalyzer
=========

Logalyzer is a script I wrote to make looking through the auth logs neater.  It can parse users, IP addresses, failures, etc.

Some examples:

<pre>
# python logalyzer.py -h
Usage: logalyzer.py [options]

Options:
  -h, --help  show this help message and exit
  -u          Specify user.  Blank lists all users.
  --full      Full log dump for specified user
  -l LOG      Specify log file.  Default is auth.log
  -f          List failures
  -s          List success logs
  -c          List commands by user
  -i          List IP Addresses

Combine flags to view user-specific information.  '-u test -i' lists IP
addresses associated with user test

# sudo python logalyzer.py -u bryan
[!] Log file:  /var/log/auth.log
[!] Logs associated with user 'bryan'
[+] First log:  Jul 24 21:26:09
[+] Last log:  Jul 24 23:38:26
[!] Failure Logs
[!] Success Logs
[!] Associated IPs
    192.168.1.118
[!] Commands
	/usr/bin/apt-get dist-upgrade
	/usr/local/bin/python logalyzer.py -l /var/log/auth.log.1 -u bryan
	/usr/local/bin/python logalyzer.py -u bryan -l /var/log/auth.log.1 -s

# python logalyzer.py -l /var/log/auth.log.1 -u bryan -c
[!] Log file:  /var/log/auth.log.1
[+] Commands for user 'bryan'
	/usr/bin/apt-get update
	/usr/bin/apt-get dist-upgrade
</pre>
