## Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.
![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the yml. file may be used to install only certain pieces of it, such as Filebeat.
  - _TODO: Enter the playbook file.  intsall-elk.yml
This document contains the following details:
- Description of the Topology: 
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build
### Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly efficient, in addition to restricting Downtime to the network.
- _TODO: What aspect of security do load balancers protect? It can help from large DDos attack and can help your network. Such as SYN flood or UDP relection. What is the advantage of a jump box?_  Because it is a secure computer  that all admin first connect before launching any admin tasks.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the monitoring and system Security.
- _TODO: What does Filebeat watches files logs
 _
- _TODO: What does Metricbeat record metrics collect statistics ship to NMS like Kibana
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.
| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
|Jump Box  | server   | 10.0.0.4   | Linux ubuntu 18.4      |
| Web-1    | server   | 10.0.0.5   | Linux ubuntu 18.4      |
| Web-2    | server   | 10.0.0.6   | Linux ubuntu 18.4      |
| Web-3    | server   | 10.0.0.7   | Linux ubuntu 18.4      |
### Access Policies
The machines on the internal network are not exposed to the public Internet. 
Only the _Jump Box____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_
Machines within the network can only be accessed by _SSH____.
- _TODO: Which machine did you allow to access yo|
### Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- No special coding skills: What is the main advantage of automating configuration with Ansible?_ Is that you can put many commands into multiple servers from one play-book and save time. It also reduces mistake.
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; Gathering Facts;
       Install docker.io;
       Install python3-pip;Install Docker module;
       Increase virtual memory;
       download and launch a docker elk container;
       enable service docker on boot
 
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

 
### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _: List the IP addresses of the machines you are monitoring_
Wep-1 10.0.0.5; web-2 10.0.0.6; web-3 10.0.0.7
We have installed the following Beats on these machines:
- _Filebeat & Meticbeat: Specify which Beats you successfully installed_
These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc.
Filebeat: collect data about the file system, it collect patterns and activities.
Metricbeat: collects machine metrics, such as uptimes. Network traffic from the Kabana like logs, from common servers, container , and services. They also montor system log
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 
SSH into the control node and follow the steps below:
- Copy the _filebeat-config.yml____ file to etc/ansible/files____
- Update the hosts_____ file to include...
- Run the playbook, and navigate to etc/ansible# ansible-playbook install-elk.yml ____ to check that the installation worked as expected.
_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? “install-elk.yml” Where do you copy it? “roles file”_ 
- _Which file do you update to make Ansible run the playbook on a specific machine? “hosts files”

 How do I specify which machine to install the ELK server on? From ansible Nano Hosts file to add the elk vm ip address 10.1.0.4 and /usr/bin/
python3 under uncommented ELK//

versus which to install Filebeat on: “nano /etc/ansible/hosts add IP of the machine to receive the filebeat under the webserver group and /usr/bin/python3”
 

- _Which URL do you navigate to in order to check that the ELK server is running? “http://ELK “VM public IP/app/kibana”
_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._ 
SSh user@Jump-Box – Pubic-IP
Sudo docker start ansible container
Sudo dockerl attach ansible container

root@ cd /etc/ansible#
root@:~ etc/ansible # ansible-playbook install-elk.yml
ssh username@ip for the elk.VM
ssh {username}@{elkserver_IP}
nmap -Pn 80{elkserver pubic IP}
sudo snap install nmap
sudo docker ps
curl http://localhost:5601/app/ki

