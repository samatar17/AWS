AWS Learning Journey 
This repository documents my AWS assignments and hands-on practice as part of my DevOps learning journey.
These assignments were not always straightforward. I ran into several problems along the way, especially during Assignment 2. I had to troubleshoot, test different solutions and keep going until I understood what was wrong and got things working.


Assignment 1 – EC2 and NGINX
What I Built:
For Assignment 1, I created an AWS EC2 instance running Ubuntu and configured it as a web server using NGINX.
I worked with:
- EC2
- Ubuntu
- Security Groups
- SSH
- HTTP
- NGINX
- AWS networking

What Worked
I successfully:
- Launched an Ubuntu EC2 instance
- Connected to the server
- Configured the Security Group
- Allowed SSH traffic on port 22
- Allowed HTTP traffic on port 80
- Installed NGINX
- Started the NGINX service
- Accessed the server through its public IP address
- Confirmed that the NGINX web page was working

Seeing the NGINX page load successfully in the browser confirmed that my EC2 instance and networking configuration were working.

Problems I Faced
Not everything worked immediately.
I had to understand how Security Groups worked and make sure the correct ports were open.
I also had to make sure NGINX was installed and running correctly before the web page could be accessed.
When something did not work, I went back through the configuration instead of starting everything again.

 How I Fixed the Problems
I checked:
- The EC2 instance status
- Security Group inbound rules
- SSH access
- HTTP port 80
- NGINX installation
- NGINX service status
- The public IP address
By checking each part step by step, I was able to find the problems and eventually get the web server working.
Completing Assignment 1 gave me more confidence using AWS EC2.

Assignment 2 – AWS Multi-Tier Network
Assignment 2 was much more challenging.
I built a network containing public and private AWS resources and had to understand how the different components communicated with each other.
What I Built
- VPC
- Public subnet
- Private subnets
- Public EC2 server
- Private EC2 web servers
- Security Groups
- Route Tables
- Internet Gateway
- NAT Gateway
- Application Load Balancer
- Target Groups
- Health Checks
- SSH
- NGINX
I also used the public server as a way of connecting to the private servers.

The Biggest Challenge – Unhealthy Servers
One of the biggest problems I faced was that both private web servers showed as Unhealthy in the Load Balancer Target Group.
The health check was configured to use:
- HTTP
- Port 80
- Path `/`
At first, I expected the servers to become healthy, but they didn't.
This became one of the most difficult parts of the assignment.


Troubleshooting the Connection
I checked the Security Group and made sure the required HTTP and SSH rules were configured.
I then tried connecting from the public server to the private server.
I tested the private IP address using `curl`, but the connection timed out.
This showed me that there was still a networking or server configuration problem.
Instead of guessing, I started checking the infrastructure one part at a time.


SSH Into the Private Server
I successfully used the public server to SSH into one of the private EC2 servers.
This was important because it proved that I could reach the private server through the public server.
Once inside the private server, I discovered another major problem.
NGINX was not installed.

 NGINX Installation Problem
I tried to install NGINX, but the package update failed.
The private server could not access the internet.
I tested the connection and found that the server was not able to reach the internet.
This explained why I could not install the packages I needed.


NAT Gateway Troubleshooting
I then investigated the NAT Gateway and routing configuration.
I checked:
- The private subnet
- Private Route Table
- The `0.0.0.0/0` route
- NAT Gateway
- Public subnet
- Security Groups
- Network connectivity
This taught me that simply creating AWS resources is not enough.
The routing between them must also be configured correctly.
I had to keep checking the path that traffic was taking and understand why the private EC2 instances could not reach the internet.

Application Load Balancer Troubleshooting
I also worked with an Application Load Balancer and Target Group.
When the instances showed as unhealthy, I had to understand that the Load Balancer needed to successfully communicate with the web servers on port 80.
This meant checking several different parts of the infrastructure rather than assuming the Load Balancer itself was the problem.
I checked the Target Group, Health Check settings, Security Groups, private servers and networking configuration.



What I Learned From the Problems
Assignment 2 was difficult because one incorrect configuration could affect several other AWS resources.
At different points I experienced:
- Unhealthy Target Group instances
- HTTP connection timeouts
- SSH connection problems
- NGINX not being installed
- Private servers without internet access
- Package installation failures
- Security Group configuration issues
- Routing and NAT Gateway troubleshooting
- EC2 connection problems
There were moments where fixing one problem led me to discover another problem.
This made the assignment take longer than I expected, but it also made it much more useful.
Instead of only following instructions, I started understanding how the different AWS services depended on each other.


Getting Everything Working
The most important thing I learned was not to give up when something didn't work.
I kept checking the infrastructure step by step:
EC2 → Security Groups → Subnets → Route Tables → NAT Gateway → NGINX → Target Group → Load Balancer
It was challenging and sometimes frustrating because I had to go back through configurations several times.
But I kept troubleshooting until I was able to complete the assignment.
Getting to the end after dealing with all the problems was one of the most valuable parts of the project.


What I Learned Overall
Through Assignments 1 and 2, I have gained hands-on experience with AWS rather than only learning the theory.
I now have a better understanding of:
- EC2 instances
- Linux servers
- VPC networking
- Public and private subnets
- Security Groups
- Route Tables
- NAT Gateways
- Load Balancers
- Target Groups
- Health Checks
- SSH
- NGINX
- Troubleshooting cloud infrastructure
Most importantly, I learned that troubleshooting is a major part of working with cloud infrastructure.
When something fails, I now know to break the problem down, test each part and work through it step by step.
