\# Install MariaDB server

sudo dnf install mariadb-server -y



\# Or for older systems:

sudo yum install mariadb-server -y



\# Enable but don't start the service yet

sudo systemctl enable MariaDB





\#details about enforce



getenforce

ls -Zd /var/log/MariaDB



ls -Z /var/lib/mysql/



seinfo -t | grep MySQL



sesearch -A -t mysqld\_exec\_t

sesearch -A -t mysqld\_db\_t

sesearch -A -t mysqld\_var\_run\_t



\# Start MariaDB service

sudo systemctl start mariadb



\# Check status

sudo systemctl status mariadb



\# Verify it's running and check its SELinux context

ps -eZ | grep mysql



\#Stop service



sudo systemctl stop mariadb



\# Verify it's stopped

sudo systemctl status MariaDB



\#Create custom directory



\# Create the new data directory

sudo mkdir -p /data/mysql



\# Check its current SELinux context

ls -Zd /data/mysql



\# You should see something like: unconfined\_u:object\_r:default\_t:s0

\# Copy existing data to new location (preserving permissions)

sudo cp -R /var/lib/mysql/\* /data/mysql/



\# Or move the data (more risky - backup first!)

\# sudo mv /var/lib/mysql/\* /data/mysql/



\# Change ownership to mysql user

sudo chown -R mysql:mysql /data/mysql



\# Verify the files are there

ls -la /data/mysql/



\# Check SELinux context of the moved files

ls -Z /data/mysql/







\# Try to start MariaDB - this should fail

sudo systemctl restart mariadb



\# Check the status and error messages

sudo systemctl status mariadb



\# Check system logs for errors

sudo journalctl -u mariadb -f







\#temp fix



\# Manually change the context (temporary fix)

sudo chcon -R -t mysqld\_db\_t /data/mysql



\# Verify the context change

ls -Zd /data/mysql

ls -Z /data/mysql/



\# Try starting MySQL again

sudo systemctl start mariadb



\# Check if it starts successfully

sudo systemctl status MariaDB



\#Revert back

\# Stop MySQL

sudo systemctl stop mariadb



\# Reset contexts to default (this will break it again)

sudo restorecon -R /data/mysql



\# Check the context - it should revert to default\_t

ls -Zd /data/mysql



\# Try to start MySQL - it should fail again

sudo systemctl start mariadb



\# This demonstrates why we need persistent context rules







