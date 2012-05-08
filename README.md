logalyzer
=========

Logalyzer is a script I wrote to make looking through the auth logs neater.  It can parse users, IP addresses, failures, etc.

Some examples:

<pre>
#:./logalyzer.py -h 
Usage: logalyzer.py [options]

Options:
  -h, --help  show this help message and exit
  -u          Specify user.  Blank lists all users.
  --full      Full log dump for specified user
  -l LOG      Specify log file.  Default is auth.log
  -f          List failures
  -c          List commands by user
  -i          List IP Addresses

  Combine flags to view user-specific information.  '-u test -i' lists IP
  addresses associated with user test

#:./logalyzer.py -u bryan
[+] Logs associated with user 'bryan'
FAILURE LOGS
SUCCESS LOGS
ASSOCIATED IPs
	192.168.1.118
COMMANDS
	/usr/bin/unlink /usr/bin/python
	/usr/bin/vim /var/log/auth.log
</pre>

You can parse addresses/commands/failures per user or in general.  
