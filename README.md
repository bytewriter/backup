# Mel - 2018-11-14
This set of backup scripts was designed to be run on mutliple servers with a
common SAN. All servers mount the same SAN directory as /backup. All servers
run the same scripts from /backup/bin. All servers read the same config file
from /backup/conf, reading the same language file in /backup/languages, and 
coordinate backing up the same list of remote systems. This was backing up 
131 systems successfully for over 6 years before the company was bought.

This set of scripts does not employ encryption through ssh or otherwise. It
didn't matter at the time, because the goal was to get working backups in a
reasonably secure way over our LAN/WAN. And at that point in time, LAN was
considered trusted, and since we didn't have many windows computers on our 
network. If writing it now, I would employ ssh to encrypt all traffic (see 
later scripts). I have not tested more than 2 backup servers sharing the 
backup tasks. It successfully backed up linux and windows (using deltacopy), 
including the MSSQL server doing it's own local backup, and this script just 
watched for the change before pulling from it.

