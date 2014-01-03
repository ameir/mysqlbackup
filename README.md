Backup Your MySQL Databases to Disk, FTP, and Email
===========
  
This is a shell script that backs up your MySQL servers.  It can talk to as many servers as you'd like (remote or local), and has some features to filter out specific databases and table names.

### Requirements
To backup databases locally, you'll only need bash and gzip, which ship with just about all Linux distros.

To backup to FTP, you'll need the 'ftp' program.

To backup to email, you'll need the 'mutt' program.

### Available options
#### MySQL Settings
##### DBNAMES
Databases you want to backup, separated by a space; leave empty to backup all databases on this host.
###### Example:
`DBNAMES[0]="db1 db2"`

##### DBUSER
Your MySQL username.
###### Example:
`DBUSER[0]="root"`

##### DBPASS
Your MySQL password.
###### Example:
`DBPASS[0]="password"`

##### DBHOST
Your MySQL server's location (IP address is best).
###### Example:
`DBHOST[0]="localhost"`

##### DBTABLES
Tables you want to backup or exclude, separated by a space; leave empty to back up all tables.
###### Example:
`DBTABLES[0]="db1.table1 db1.table2 db2.table1"`

##### DBTABLESMATCH
If you set this to 'include', it will backup ONLY the tables in DBTABLES, 'exclude' will backup all tables BUT those in DBTABLES.
###### Example:
`DBTABLESMATCH[0]="include"`

##### DBOPTIONS
If you want to give `mysqldump` other options, include them here.
###### Example:
`DBOPTIONS[0]="--quick --single-transaction"`

#### Email Settings
##### EMAILS
Email addresses to send backups to, separated by a space.
###### Example:
`EMAILS="address@yahoo.com address@usa.com"`

##### SUBJECT
This is the subject of the email that you'll get.
###### Example:
`SUBJECT="MySQL backup on $SERVER ($DATE)"`

#### FTP Settings
##### FTPHOST
###### Example:
`FTPHOST[0]="ftphost"`

##### FTPUSER
###### Example:
`FTPUSER[0]="username"`

##### FTPPASS
###### Example:
`FTPPASS[0]="password"`

##### FTPDIR
###### Example:
`FTPDIR[0]="backups"`

### Backing up multiple servers
For each server you're backing up, you will need to copy/paste the block under `MySQL Settings` and increment the key in brackets (e.g. the first server will be 0, the next will be 1, and so on).