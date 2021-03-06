## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Diagram](https://raw.githubusercontent.com/LundJim/Project1/main/Diagrams/2-21-22%20Project%201.PNG)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Playbook file may be used to install only certain pieces of it, such as Filebeat.

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

Load balancers monitor web traffic and ensure servers do not get overwhelmed. Jumpbox allows for security between two network zones.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the web activity and system logs.
- Filebeat monitors system log data.
- Metricbeat gathers metrics and sends them to specific ouput.

The configuration details of each machine may be found below.

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
- Jumpbox 10.0.0.4, Web 1 10.0.0.7, Web 2 10.0.0.6, Web 3 10.0.0.8, ELK Virtual Machine 10.1.0.4 

Machines within the network can only be accessed by Docker Container.
- Jumpbox and the IP address 10.1.0.4. 

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.4             |
| ELK      | No                  | 10.1.0.4             |
| Web 1    | No                  | 10.0.0.7             |                                        
| Web 2    | No                  | 10.0.0.6             |   
| Web 3    | No                  | 10.0.0.8             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it allows different systems to communicate through configuration and easy to develop and access.

The playbook implements the following tasks: 
-  Use apt module to install docker.io, 
-  use apt module to install pip3,
-  use pip module to install docker python module,
-  use system control module to use more memory
-  use docker_container module to download and launch a docker elk container and use systemd module to enable service on the root.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![dockerpsoutput](https://raw.githubusercontent.com/LundJim/Project1/main/Dockerpsoutput.PNG)


### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web 1 10.0.0.7 
- Web 2 10.0.0.6 
- Web 3 10.0.0.8

We have installed the following Beats on these machines:
- MetricBeat and Filebeat

These Beats allow us to collect the following information from each machine:
- Filebeat reviews log files and events and I would expect to see it get sent to Elasticsearch or Logstash for additional analysis. 
- Metricbeat watches servers and collects metrics and I would expect to see it send information to Logstash for additional review.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the host file to environment.
- Update the host file to include the correct group and ip addresses.
- Ran the playbook, and navigate to Kibana to check that the installation worked as expected.

Answer the following questions to fill in the blanks:1
- The yml file in the Host file.
- Docker and Elkstack
- http://23.100.87.169:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

<<<<<<< HEAD
The following sources were used:

Trilogy Education Services, a 2U, Inc. Brand

elastic.co

digitalocean.com

=======
Resources used:
Trilogy Education Services, a 2U, Inc. Brand
elastic.co
digitalocean.com


>>>>>>> 0e8d45b1b0d6f5280324bc3d656c3449ae658470
---
