# **Lab 0 Module 1: EC2 Deployment**
For this lab, we started by making a security group and launch template:
<img width="2059" height="1065" alt="1" src="https://github.com/user-attachments/assets/df1b441e-a3ab-423c-8fe1-ae980ea6f279" />
<img width="2237" height="725" alt="2" src="https://github.com/user-attachments/assets/590328e4-053b-446f-a3a1-03471b24dda9" />


## **Deployment 1**
We launched the instance from the saved template shown above. After waiting for the checks to complete, we connected via EC2 Instance Connect (browser-based). Simple process that allowed us to login directly from our user account. Once in, we could see a number of details on the SEIR dashboard: such as CPU, hostname, memory, root disk, and many more details. Once done, we terminated the instance.
<img width="2112" height="1073" alt="3" src="https://github.com/user-attachments/assets/60d86dcb-bd65-4e67-9315-db9c2942cc5e" />
<img width="550" height="498" alt="5" src="https://github.com/user-attachments/assets/91608b9c-4116-461a-9c77-b8130c68c78d" />


## **Deployment 2**
For the second deployment, we connected to our instance via SSH using Gitbash. We were given a couple of commands; one for changing the permissions of the key pair file, and another for logging into our specific user account from our local terminal. Doing this procedure helped to solidify my understanding of SSH and how it works with the AWS architecture. Just like deployment 1, after logging in, we were able to see the SEIR dashboard details. Instance was terminated shortly after.
<img width="2057" height="1061" alt="6" src="https://github.com/user-attachments/assets/93bb4d3c-3e3b-4e4f-bf9b-7d31aa3417e6" />
<img width="564" height="531" alt="8" src="https://github.com/user-attachments/assets/445afdb3-e2fa-43c0-b47e-62b84c2ea822" />


## **Deployment 3**
Same as the second deployment, we accessed the instance via SSH using Gitbash. After the third time, the process was fluid. Termination of all instances complete.
<img width="2043" height="1063" alt="9" src="https://github.com/user-attachments/assets/97b14743-e606-4055-ab94-dcc6bcaf6127" />
<img width="548" height="528" alt="11" src="https://github.com/user-attachments/assets/ed49c9f9-7e29-4b73-acf7-6f4e19641a79" />
<img width="2525" height="1160" alt="12" src="https://github.com/user-attachments/assets/1e26ecbe-017d-4139-a138-7b2d90b2ef79" />


## **Dashboard Details**
CPU: Brain of the computer. Shows the percentage of processing power being used at that time. All instances showed 0% since the only thing being ran was the webpage.

Memory: RAM (Short-term space). Holds data and programs you're actively using right now for the CPU. All instances had less than 20% memory usage, so runtime was smooth.

Disk usage (SSD/HDD): Long-term storage for saving files, folders, photos, etc. All instances had only 21% of the disk space full. Plenty of space to use for storing anything needed. 

Uptime: Amount of time said device has been running since the last boot or restart. All instances were up 5 minutes or less, decreasing costs in the process.


## **Repitition**
The ability to correctly SSH into EC2 instance via a local terminal is an important skill that I can say I'm now confident in performing. 


## **Errors**
Only error I ran into during the lab was accessing the webpage. I forgot to add in the "http://" when searching for the page since port 80 was turned on for the security group. After adding it in, the webpage came up instantly.


## **Deployment Table**
| Deployment | Public IPv4 address | Connection method | Screenshot | Instance terminated? |
|---|---|---|---|---|
| 1 | `3.21.231.53` | EC2 Connect | [screenshots/deployment-1.png](https://github.com/sroscoe904/SEIR-Foundations-HW/blob/main/module1/lab0_basics/screenshots/deployment-1.png) | Yes |
| 2 | `13.184.21.219` | SSH | [screenshots/deployment-2.png](https://github.com/sroscoe904/SEIR-Foundations-HW/blob/main/module1/lab0_basics/screenshots/deployment-2.png) | Yes |
| 3 | `52.14.66.151` | SSH | [screenshots/deployment-3.png](https://github.com/sroscoe904/SEIR-Foundations-HW/blob/main/module1/lab0_basics/screenshots/deployment-3.png) | Yes |
