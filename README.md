# Ansible-Roles
Configure webserver and Haproxy LoadBalancer
🔅Create an ansible role myapache to configure Httpd WebServer.
🔅Create another ansible role myloadbalancer to configure HAProxy LB.
🔅We need to combine both of these roles controlling webserver versions
and solving challenge for host ip’s addition dynamically over each Managed
Node in HAProxy.cfg file.
![image](https://user-images.githubusercontent.com/68059131/138924511-5dea3e1b-3562-49c7-9a7f-4b308ed87d10.png)
What is ansible?
Ansible is an open source IT Configuration Management, Deployment & Orchestration tool. It aims to provide large productivity gains to a wide variety of automation challenges. This tool is very simple to use yet powerful enough to automate complex multi-tier IT application environments.
Ansible Terms:
Controller Machine: The machine where Ansible is installed, responsible for running the provisioning on the servers you are managing.
Inventory: An initialization file that contains information about the servers you are managing.
Playbook: The entry point for Ansible provisioning, where the automation is defined through tasks using YAML format.
Task: A block that defines a single procedure to be executed, e.g. Install a package.
Module: A module typically abstracts a system task, like dealing with packages or creating and changing files. Ansible has a multitude of built-in modules, but you can also create custom ones.
Role: A pre-defined way for organizing playbooks and other files in order to facilitate sharing and reusing portions of a provisioning.
Play: A provisioning executed from start to finish is called a play. In simple words, execution of a playbook is called a play.
Facts: Global variables containing information about the system, like network interfaces or operating system.
Handlers: Used to trigger service status changes, like restarting or stopping a service.
Ansible is a helpful tool that allows you to create groups of machines, describe how these machines should be configured or what actions should be taken on them. Ansible issues all commands from a central location to perform these tasks.
Today we are going to use Ansible Role’s:
To Perform this practical i have created two roles;
Myapache (To configure webserver)
Mylb ()
![image](https://user-images.githubusercontent.com/68059131/138924568-d9c01de3-3257-47b1-a5f1-103063787f21.png)
Command to create ansible roles are :
ansible-galaxy role init myapache
ansible-galaxy role init mylb
First go inside myapache 👇
![image](https://user-images.githubusercontent.com/68059131/138924640-56d96483-0c3d-473e-858e-3e6b7287bb17.png)
Task 👇
![image](https://user-images.githubusercontent.com/68059131/138924680-63596d17-4882-4e74-b66e-f658ba3d8d8b.png)
Templates 👇
![image](https://user-images.githubusercontent.com/68059131/138924860-c7149aca-ba12-4348-a005-e845aa02d2a7.png)
Vars 👇
![image](https://user-images.githubusercontent.com/68059131/138924900-538cb4d4-4042-46b8-b2b6-7378e39d34a8.png)
Let’s go inside mylb 👇
![image](https://user-images.githubusercontent.com/68059131/138924946-11ea95f7-6d5b-4ece-bb29-9cd3f8e6a7ac.png)
Task 👇
![image](https://user-images.githubusercontent.com/68059131/138925028-2b5352f5-6ca4-490c-a905-f237b6070d0d.png)
Templates 👇
![image](https://user-images.githubusercontent.com/68059131/138925105-8abef978-9040-4652-a49c-1e180c477836.png)
Now we have to set our roles path into the ansible configuration file.
vim /etc/ansible/ansible.cfg
![image](https://user-images.githubusercontent.com/68059131/138925170-9496f195-e1af-4f8e-9802-8afd90bf4163.png)
Now come to final step:
To run our roles we have to create create a directory , inside it i have created a file setup.yml in which i created a playbook which will run my roles.
Directory 👇
![image](https://user-images.githubusercontent.com/68059131/138925213-d74250f5-d95f-4a41-a9dd-b7775df55b4f.png)
Setup.yml 👇
![image](https://user-images.githubusercontent.com/68059131/138925278-8e524c52-d2d3-4067-82c8-c8d9fc5c7269.png)
Final Step is Run the playbook “ansible-playbook setup.yml”
To see the complete demonstration please visit to this link here i have made a video: 👇
https://www.linkedin.com/posts/swarnim-kashyap-b99405185_vimaldaga-righteducation-educationredefine-activity-6781506847561015296-tGEK
![image](https://user-images.githubusercontent.com/68059131/138925329-6b3b09f3-3d16-4b7c-9645-6b5aa5480c7a.png)
