Run 1

Instance ID: i-0f56055ac1936da2b

Public DNS (IPv4): ec2-3-87-78-247.compute-1.amazonaws.com

Boot Time: 2026-10-30 22:54:37

Unique line of run: INFO:     Started server process [37545]

Three things learned: Whenever I clicked on an option in the banking API, there was a GET request sent to the terminal in the form of a 200 code, which means the request was successful. 
After researching what a 'favicon' is, I realized the 404 error I received had nothing to do with the banking app itself. There just wasn't a favicon file (website logo) for this particular interface. 
Only error I came across in this run was trying to copy commands within terminal using CTRL-C instead of just copy and pasting them from the runbook. 
What changed from the runbook was running the "uptime -s" command to figure out the boot time of the machine. I tested it against the "date -u" command to check and make sure it displayed in UTC time. 
Instance was terminated and there were no leftover resources. 

Run 2

Instance ID: i-01190c552a22032ef

Public DNS (IPv4): ec2-184-198-223-252.compute-1.amazonaws.com

Boot Time: 2026-10-31 15:07:52

Unique line of run: INFO:     Started server process [36016]

Three things learned: What changed in this run was server's PID. I believe this is unique to each startup of the banking API since the first was 37545 and this one was 36016.
No errors occurred in this run. I learned that clicking on the command in the banking interface executes a GET HTTP request for the different, being the terminal in this case. Instance was terminated and no leftover resources were found.

Run 3

Instance ID: i-0a7b691434925f427

Public DNS (IPv4): ec2-54-242-134-179.compute-1.amazonaws.com

Boot Time: 2026-11-01 00:43:14

Unique line of run: INFO:     Started server process [35962]

Three things learned: You can clone your own repo on virtually any EC2 with the git clone command. No errors happened in this run. What changed in this run was the payment post when I tried changing the account number for Alice Johnson. It came back with a REJECTED message, letting me know the account didn't exist. Instance was terminated and no resources were left behind.


Run 4

Instance ID: i-06d2b5b67d9d11dc9

Public DNS (IPv4): ec2-54-89-203-233.compute-1.amazonaws.com

Boot Time: 2026-11-01 15:00:17

Unique line of run: INFO:     Started server process [37313]

Three things learned: No errors occurred in this run. Instance was terminated and no resources were left behind.

Run 5

Instance ID: i-0ea77c059523a85a2

Public DNS (IPv4): ec2-98-81-192-224.compute-1.amazonaws.com

Boot Time: 2026-11-01 18:45:56

Unique line of run: INFO:     Started server process [36574]

Three things learned: In the banking interface, /ask and /payments are POST HTTP request, meaning they're sending your entries (data) to the server. No errors occurred in this run. Instance terminated and no resources were left behind. What changed in this run was when I tried editing the value of the schema in /ask to a question and got a "422 Unprocessable Entity" error. I just had to flip them around. Instead of typing in the question in the "question" field, I instead typed it in the "string" field and got the 200 OK HTTP code.

Run 6
Instance ID: 
Public DNS (IPv4):
Boot Time:
Unique line of run: 
Three things learned: You can create different account 

Run 7
Instance ID: 
Public DNS (IPv4):
Boot Time:
Unique line of run: 
Three things learned:



COBOL Practice:


Mistakes I made:
Trying to copy commands from within the terminal and pasting them using CTRL-C instead of just copy and pasting them from the runbook.
Tried editing the value of the schema in /ask to a question and got a "422 Unprocessable Entity" error.




Commands I know by heart:
whoami
date
uptime -s
