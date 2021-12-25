## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Project1Elkdiagram](LINK TO DIAGRAM HERE)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - [Ansible Playbook](https://github.com/LundJim/Project1/tree/main/Ansible)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly secure, in addition to restricting internet access to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for? Monitors system log data
- _TODO: What does Metricbeat record?  Gathers metrics and sends them to specific ouput.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| ElkServer| Kibana   | 10.1.0.4   | Linux            |
| Web1     | DVWA     | 10.0.0.7   | Linux            |
| Web2     | DVWA     | 10.0.0.6   | Linux            |
| Web3     | DVWA     | 10.0.0.8   | Linux            |
 
### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the host machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Add whitelisted IP addresses_Jumpbox 10.0.0.4, Web 1 10.0.0.7, Web 2 10.0.0.6, Web 3 10.0.0.8, ELK Virtual Machine 10.1.0.4 

Machines within the network can only be accessed by Docker Container.
- Which machine did you allow to access your ELK VM? Jumpbox What was its IP address? Private 

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 10.0.0.1 10.0.0.2    |
| Load Bal.|                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible? Allows different systems to communicate through configuration

The playbook implements the following tasks:
-  In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
-  Use apt module to install docker.io, 
-  use apt module to install pip3,
-  use pip module to install docker python module,
-  use system control module to use more memory
-  use docker_container module to download and launch a docker elk container and use systemd module to enable service on the boot.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![dockerpsoutput](https://raw.githubusercontent.com/LundJim/Project1/main/Dockerpsoutput.PNG)


### Target Machines & Beats
This ELK server is configured to monitor the following machines: Jumpboxclass and ELKM
- _TODO: List the IP addresses of the machines you are monitoring_ 10.1.0.0.4 and 40.122.108.197

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._