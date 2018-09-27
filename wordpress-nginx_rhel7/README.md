## WordPress+Nginx+PHP-FPM+MariaDB Deployment

- Requires Ansible 2.6 or newer
- Expects CentOS/RHEL 7.x host/s

RHEL7 version reflects changes in Red Hat Enterprise Linux 7:
1. Network device naming scheme has changed
2. iptables is replaced with firewalld
3. MySQL is replaced with MariaDB
4. The configuration is now using the latest WordPress as of 20180926
5. Red Hat Software Collection is used to deliver nginx 1.12 and MariaDB 10.2
6. RHEL7 delivers PHP 5.4 

These playbooks deploy a simple all-in-one configuration of the popular WordPress blogging platform and CMS, frontend by the Nginx web server and the PHP-FPM process manager. The playbooks provide insight into a realistic deployment of the software. Look in the files for additional comments about choices and possibilities. Your L/100km will vary with the platform and network environment you deploy in. Remember these are examples, modified to do some work in my lab. These are not production ready playbooks.

To run the playbooks, create a simple inventory file, called 'inventory' (or whatever you like) that looks like this.

	[wordpress-servers]
	yourfqdn.goes.here

You also should go into the group_vars directory and edit the 'all' file. This contains the variables that are critical to the configuration. Remember that if you overide these at that commandline and if you are using Ansible Tower, you can configure them in the Job definition or ask for them through a Survey.

For the commandline, run the playbook like this:

	ansible-playbook -i inventory main.yml

The playbooks will configure MariaDB, WordPress, Nginx, and PHP-FPM. When the run is complete, you can hit your configured server name to begin the WordPress configuration.

### Ideas for Improvement

Here are some ideas for ways that these playbooks could be extended:

- Parameterize the WordPress deployment to handle multi-site configurations.
- Separate the components (PHP-FPM, MySQL, Nginx) onto separate hosts and 
handle the configuration appropriately.
- Handle WordPress upgrades automatically.

Like the original authors, I would love to see contributions and improvements, so please fork this repository on GitHub and send us your changes via pull requests.
