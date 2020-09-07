## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Network Diagram](https://github.com/jesoriano81/Project-1/blob/master/Diagrams/Network%20Diagram.pdf)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Project 1 file may be used to install only certain pieces of it, such as Filebeat.

  - _install_web.yml_

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly useable, in addition to restricting DDOS to the network.
- Load balancing is the process of distributing network traffic across multiple servers. This ensures no single server bears too much demand. By spreading the work evenly, load balancing improves application responsiveness. It also increases availability of applications and websites for users. Why use a jump box? Reducing the subnet size (increasing the number of subnets), and securing those VLANs using a firewall or router. Using higher security authentication, such as multi-factor authentication. Keeping the operating system and software on the jump server up to date.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
-Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
- Metricbeat is a lightweight shipper that collects and ships various system and service metrics to a specified output destination.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name          | Function  | IP Address   | Operating System |
|---------------|-----------|--------------|------------------|
| Jump Box      | Gateway   | 10.0.0.4     | Linux            |
| Load Balancer | Container | 13.92.40.250 | Linux            |
| Web-1         | Sever     | 10.0.0.7     | Linux            |
| Web-2         | Sever     | 10.0.0.8     | Linux            |


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Load Balancer machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 10.0.0.4
- 10.0.0.7
- 10.0.0.8

Machines within the network can only be accessed by Jump Box.
- Jump Box 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name          | Publicly Accessible | Allowed IP Addresses |
|---------------|---------------------|----------------------|
| Load Balancer | yes                 | 13.92.40.250         |
| Web-1         | No                  | 10.0.0.7             |
| Web-2         | No                  | 10.0.0.8             |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Using Ansible makes it easier to create computer software and processes.

The playbook implements the following tasks:
-
- ...Create a container.
- ...write a yml playbook.
- ...Install Docker
- ...Download and launch dvwa image


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _10.0.0.7
- _10.0.0.8

We have installed the following Beats on these machines:
- File Beat & Metric beat.

These Beats allow us to collect the following information from each machine:
- Using the metric beat you get system-level CPU usage, memory, file system, disk IO, and network IO statistics, as well as top-like statistics for every process running on your systems. File beat forwards and centrallizes log data, it monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the install_web.yml file to web-1 & 2 servers.
- Update the install_web.yml file to include...
- Run the playbook, and navigate to Red_LoadB to check that the installation worked as expected.

- _After using the install_web.yml file copy the file over to the web sever 1 & 2_
- _Update the file in the container to effect the other machines. _
