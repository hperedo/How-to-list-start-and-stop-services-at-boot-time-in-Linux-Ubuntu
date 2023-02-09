# How-to-list-start-and-stop-services-at-boot-time-in-Linux-Ubuntu
How to list, start and stop services at boot time in Linux Ubuntu

1.List startup services at boot time
There are many options that allow us to see the list of services at boot time. We will outline below the most commonly used tools.
To list out all services along with their corresponding statuses using systemct , open up your terminal and type in the command below

# systemctl -at service

To single out only those services that are active

# systemctl -t service --state=active

For the services that are enabled

# systemctl list-unit-files --state=enabled

An alternative to the command above using piping/grep

# systemctl list-unit-files | grep enabled

To display the list of all currently loaded service units

# systemctl list-units --type service

To display a list of all loaded units (all states)

# systemctl list-units --type service --all

To find out the services ordered after a specified service

# systemctl list-dependencies --after 

To find out the services ordered before a specified service

# systemctl list-dependencies --before 

The ‘service’ command utility allows to start, restart and stop and daemons as well as other services in Linux.
To display the list of all services.

# service --status-all

To check whether a specific service was enabled at boot time

# systemctl is-enabled mysql

To see the status of a given service

# systemctl status ufw

As an alternative

# systemctl list-unit-files --type service 

To enable a single service 

# sudo systemctl enable mysql

To disable a single service 

# sudo systemctl disable mysql

To start a single service 

# sudo systemctl start mysql

To stop a single service 

# sudo systemctl stop mysql

To restart a single service 

# sudo systemctl restart mysql

To check error messages or logs related to the services

# journalctl -u mongod

