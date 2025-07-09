\# List SELinux users

sudo semanage user -l



\# List SELinux roles

sudo semanage role -l



\# List user-role mappings

sudo semanage login -l



\# Create custom SELinux users with different privileges

sudo semanage user -a -r 's0-s0:c0.c1023' -R 'user\_r' clerk\_u

sudo semanage user -a -r 's0-s0:c0.c1023' -R 'user\_r staff\_r' manager\_u

sudo semanage user -a -r 's0-s0:c0.c1023' -R 'user\_r staff\_r sysadm\_r' admin\_u



\# Verify custom users

sudo semanage user -l | grep -E "(clerk\_u|manager\_u|admin\_u)"



\# Create Linux users

sudo useradd clerk1

sudo useradd manager1

sudo useradd admin1



\# Set passwords

sudo passwd clerk1

sudo passwd manager1

sudo passwd admin1



\# Map Linux users to SELinux users

sudo semanage login -a -s clerk\_u clerk1

sudo semanage login -a -s manager\_u manager1

sudo semanage login -a -s admin\_u admin1



\# Verify mappings

sudo semanage login -l | grep -E "(clerk1|manager1|admin1)"





\# Create test files with different contexts

sudo touch /tmp/user\_file

sudo touch /tmp/staff\_file

sudo touch /tmp/admin\_file



\# Set appropriate contexts (we'll use generic contexts for now)

sudo chcon -u system\_u -r object\_r -t user\_home\_t /tmp/user\_file

sudo chcon -u system\_u -r object\_r -t staff\_home\_t /tmp/staff\_file

sudo chcon -u system\_u -r object\_r -t admin\_home\_t /tmp/admin\_file



\# Test access with different roles

sudo su - clerk1

id -Z  # Should show clerk\_u:user\_r:user\_t:s0

\# Try to access files (may work depending on policy)

ls -la /tmp/\*\_file

exit



sudo su - manager1

id -Z  # Should show manager\_u:user\_r:user\_t:s0

\# Test role switching if allowed

newrole -r staff\_r  # May prompt for password

id -Z  # Should show staff\_r role

exit

exit

