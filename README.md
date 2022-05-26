# Elk-Project
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

(https://github.com/AyindeB/Elk-Project/blob/main/Diagrams/clouddiagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

- [Filebeat Playbook](https://github.com/AyindeB/Elk-Project/blob/main/ansible/Filebeat-playbook.yml)
- [Metricbeat Playbook](https://github.com/AyindeB/Elk-Project/blob/main/ansible/Metricbeat-playbook.yml)
- [Elk Install](https://github.com/AyindeB/Elk-Project/blob/main/ansible/Install-Elk.yml)
- [DVWA](https://github.com/AyindeB/Elk-Project/blob/main/ansible/dvwa)
  

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly avaliable, in addition to restricting access to the network.
- Loadbalancers protect servers in server farms to improve availability. This causes an increase in responsivness preventing issues like server overload. One goes out   the load balancer picks up the pieces in time for another server to take the load of traffic.  
- Jump boxes are a harden device used to manage and access all devices in a different zone of security. It connects to other servers or untrusted environments without   keys unlike other VMs where access through ssh is needed.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system resources.
- Filebeat handles fowarding and centralizing log data to the Elk stack
- Metricbeat takes the metrics and statistics that is collected ans ships them to Elk. It also moniters servers by collecting metrics from the system running on the 
  server.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name          | Function            | IP Address | Operating System |
|---------------|---------------------|------------|------------------|
| Jumping-Japan | Gateway             | 10.1.0.8   | Linux            |
| RedElk-VM     | Elasticsearch Stack | 10.0.0.4   | Linux            |
| Web1          | Web Server          | 10.1.0.5   | Linux            |
| Web2          | Web Server          | 10.1.0.6   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jump box provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
98.197.237.189

Machines within the network can only be accessed by the jump box. *The Elk machine can have access from personal ip through port 5601. 
- Jumping-Japan
- Public: 20.89.111.21
- Private: 10.1.0.8

A summary of the access policies in place can be found in the table below.

| Name             | Publicly Accessible | Allowed IP Addresses |
|------------------|---------------------|----------------------|
| Jump Box         | Yes                 | 98.197.237.189       |
| Web1             | No                  | 10.1.0.5             |
| Web2             | No                  | 10.1.0.6             | 
| Load Balancer    | Yes                 | 20.222.202.167       |  
| Elk              | Yes                 | 20.70.163.17         |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because 
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

[Docker ps](https://github.com/AyindeB/Elk-Project/blob/main/Images/docker%20ps-a.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web1: 10.1.0.5
- Web2: 10.1.0.6

We have installed the following Beats on these machines:
- [Filebeat]
- [Metricbeat]

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
