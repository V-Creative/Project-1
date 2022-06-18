## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

[Project-1/Homework 12.png](https://github.com/V-Creative/Project-1/blob/0dc7a5a4e88d4c171c65d50da93f579d138008e6/Homework%2012.png)
![image](https://user-images.githubusercontent.com/91346174/174458811-1f94116d-3375-41f0-b34d-e486cd83394a.png)


These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  (https://github.com/V-Creative/Project-1/blob/f5f11728e3760d7021c20bb1dcbd5c8d20601b90/Ansible/Docker/pentest.yml)

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly functional and available, in addition to restricting traffic to the network.
- _TODO: What aspect of security do load balancers protect? 
- Load balancers add resiliency by rerouting live traffic from one server to another if a server falls prey to a DDoS attack or otherwise becomes unavailable.

What is the advantage of a jump box?
- A Jump Box Provisioner is also important as it prevents Azure VMs from being exposed via a public IP Address. This allows us to do monitoring and logging on a single box. We can also restrict the IP addresses able to communicate with the Jump Box, as we've done here.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the netowrk and system log.
- _TODO: What does Filebeat watch for?
- Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
- _TODO: What does Metricbeat record?
- Metricbeat takes the metrics and statistics that it collects and ships them to the output

The configuration details of each machine may be found below.

|    Name   |   Function   |        IP Address        | Operating System |
|:---------:|:------------:|:------------------------:|:----------------:|
| Jump Box  | Gateway      | 10.1.0.4 / 20.85.232.66  | Linux            |
| Web-1     | UbuntuServer | 10.1.0.5 / 40.114.124.38 | Linux            |
| Web-2     | UbuntuServer | 10.1.0.6 / 40.114.124.38 | Linux            |
| DVWA-VM3  | UbuntuServer | 10.1.0.7 / 40.114.124.38 | Linux            |
| ELKserver | UbuntuServer | 10.2.0.4 / 20.84.136.248 | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 


Machines within the network can only be accessed by Workstation & Jump-Box-Provisioner thorough ssh.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_
- 10.1.0.4 via SSH port 22
A summary of the access policies in place can be found in the table below.

|    Name   | Publicly Accessible |           Allowed IP Addresses          |
|:---------:|:-------------------:|:---------------------------------------:|
| Jump Box  | Yes                 | 20.85.232.66 (Workstation IP on SSH 22) |
| Web-1     | No                  | 10.1.0.4 on SSH 22                      |
| Web-2     | No                  | 10.1.0.4 on SSH 22                      |
| DVWA-VM3  | No                  | 10.1.0.4 on SSH 22                      |
| ELKserver | No                  | Workstation MY Public IP using TCP 5601 |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_
- Ansible lets you quickly and easily deploy multitier applications throug a YAML playbook.
- You don't need to write custom code to automate your systems.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install Docker.io
- Install Python.pip
- Download & Launch ELK Docker Container
- Check Published ports were made avalaible

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

[Web-1](https://github.com/V-Creative/Project-1/blob/cc14de7c498302d9bf29296c263d2801505f365f/docker_ps_web1png)
![image](https://user-images.githubusercontent.com/91346174/174459748-b160a7e8-6ea6-49d5-961c-1c0955f2079e.png)


[Web-2](https://github.com/V-Creative/Project-1/blob/cc14de7c498302d9bf29296c263d2801505f365f/docker_ps_web2.png)
![image](https://user-images.githubusercontent.com/91346174/174459750-921a3b41-01e3-4f00-ae00-7c720be405ab.png)


[DVWA](https://github.com/V-Creative/Project-1/blob/cc14de7c498302d9bf29296c263d2801505f365f/docker_ps_dvwa.png)
![image](https://user-images.githubusercontent.com/91346174/174459744-c8d100a1-2310-4e6f-9883-f510c8dc75a1.png)



### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

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
