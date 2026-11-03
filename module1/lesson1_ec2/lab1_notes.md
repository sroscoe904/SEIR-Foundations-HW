Run 1
=
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
=
Instance ID: i-01190c552a22032ef

Public DNS (IPv4): ec2-184-198-223-252.compute-1.amazonaws.com

Boot Time: 2026-10-31 15:07:52

Unique line of run: INFO:     Started server process [36016]

Three things learned: What changed in this run was server's PID. I believe this is unique to each startup of the banking API since the first was 37545 and this one was 36016.
No errors occurred in this run. I learned that COBOL doesn't use decimals when outputting numbers. Instance was terminated and no leftover resources were found.



Run 3
=
Instance ID: i-0a7b691434925f427

Public DNS (IPv4): ec2-54-242-134-179.compute-1.amazonaws.com

Boot Time: 2026-11-01 00:43:14

Unique line of run: INFO:     Started server process [35962]

Three things learned: You can clone your own repo on virtually any EC2 with the git clone command. No errors happened in this run. What changed in this run was the payment post when I tried changing the account number for Alice Johnson. 
It came back with a REJECTED message, letting me know the account didn't exist. Instance was terminated and no resources were left behind.



Run 4
=
Instance ID: i-06d2b5b67d9d11dc9

Public DNS (IPv4): ec2-54-89-203-233.compute-1.amazonaws.com

Boot Time: 2026-11-01 15:00:17

Unique line of run: INFO:     Started server process [37313]

Three things learned: No errors occurred in this run. I learned that an 8 for the return code just means the command entered doesn't follow the business rules, and is therefore rejected by the system. 
Nothing changed this run. Instance was terminated and no resources were left behind.



Run 5
=
Instance ID: i-0ea77c059523a85a2

Public DNS (IPv4): ec2-98-81-192-224.compute-1.amazonaws.com

Boot Time: 2026-11-01 18:45:56

Unique line of run: INFO:     Started server process [36574]

Three things learned: In the banking interface, /ask and /payments are POST HTTP requests, meaning they're sending your entries (data) to the server. No errors occurred in this run. Instance terminated and no resources were left behind. 
What changed in this run was when I tried editing the value of the schema in /ask to a question and got a "422 Unprocessable Entity" error. I just had to flip them around. 
Instead of typing in a question where the "question" field was, I instead typed it in the "string" field and got the 200 OK HTTP code.



Run 6
=
Instance ID:  i-0a2c437d5fe863dd8

Public DNS (IPv4): ec2-98-81-173-90.compute-1.amazonaws.com

Boot Time: 2026-11-03 00:12:38

Unique line of run: INFO:     Started server process [35139]

Three things learned: While looking through the schema, I noticed that the banking application was running on SQLite, which is a lightweight version of SQL for less intensive application. 
This makes sense because the instance only needs 2GB to run this application. Nothing changed this run. No errors occurred. Instance was terminated and resources deleted.



Run 7
=
Instance ID: i-00007fc280b3d8bec

Public DNS (IPv4): ec2-34-235-128-55.compute-1.amazonaws.com

Boot Time: 2026-11-03 00:39:25

Unique line of run: INFO:     Started server process [35220]

Three things learned: I learned the command in COBOL for trying to post a payment via a test for overspending: TEST-OVERBALANCE. A error I made was trying to post a payment using the same TXN ID. Just needed to change the number at the end and it worked.
Instance was terminated and no resources were left behind.



COBOL Practice:
=
Lab Run: 7

Instance ID: i-00007fc280b3d8bec

1. Command: cat data/accounts.dat

Account IDs: 100001Alice Johnson; 100002Robert Smith; 100003Maria Garcia   

Number of Accounts: 3

2. Command: ./cobol/bin/account_lookup 100001

Exact output: 

ACCOUNT=100001

NAME=Alice Johnson

STATUS=ACTIVE

BALANCE=5000.00

CURRENCY=USD

Return code: 0

Meaning: Successful account lookup

3. Command: ./cobol/bin/account_lookup 999999

Exact output:

ERROR=ACCOUNT NOT FOUND

ACCOUNT=999999

Return code: 4

Meaning: Account requested does not exist

4. Command: ./cobol/bin/payment_post TXN-SR-0001 100001 0.00 USD TEST-ZERO

Exact output: 

TXN=TXN-SR-0001

ACCOUNT=100001

AMOUNT=0.00

CURRENCY=USD

STATUS=REJECTED

REASON: AMOUNT MUST BE GREATER THAN ZERO

Return code: 8

5. Command: ./cobol/bin/payment_post TXN-SR-0002 100001 0010000.00 USD TEST-OVERBALANCE

Exact output: 

TXN=TXN-SR-0002

ACCOUNT=100001

AMOUNT=10000.00

CURRENCY=USD

STATUS=REJECTED

REASON=INSUFFICIENT FUNDS

Return code: 8

6. Command: cd ~ && /opt/balerica-bank/cobol/bin/account_lookup 100001

Exact output:

ERROR=CANNOT OPEN data/accounts.dat

FILE-STATUS=35

Return code: 12

Meaning: Environment/file access failure

6. Fixed-Width Ledger

Alice's raw balance: 000000500000

Decoded balance: $5000.00

Decimal: There's no decimal in the output because COBOL treats the decimal point as an implied or virtual position in the number rather than storing an actual dot character.

7. Payment Journal

Command: cat data/payments.dat

TXN-SR-0001 journal entry: TXN-SR-0001         100001000000000000USDREJECTEDTEST-ZERO

TXN-SR-0002 journal entry: TXN-SR-0002         100001000001000000USDREJECTEDTEST-OVERBALANCE

Alice's balance after payment: $5000.00

Did the balance change? No

My explanation: Just because the payment was posted doesn't mean any actual money was deposited into the account. 



Mistakes I made
=
Trying to copy commands from within the terminal and pasting them using CTRL-V instead of just copy and pasting them from the runbook.
Tried editing the value of the schema in /ask to a question and got a "422 Unprocessable Entity" error.
Trying to post a payment using the same TXN ID.



Commands I know by heart 
=
whoami

date

uptime -s 

pwd

cd

cat

ls

git clone
