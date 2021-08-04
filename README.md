# mitre_simulation
Client-Server Framework to simulate MITRE techniques. 

INFO:
OS Supported - Windows, OS X, Linux Based OS(Ubuntu tested)

WorkFlow:
1. At Server side, run the main server script which initializes the UI and the API components.
2. At client side, upon configuring the server IP and executing the client script, it sends status payload to the server every two minutes and simultaneously awaits for the further commands. 
3. At server side, admin can view all active clients and it's system details and can choose a system on which simulation needs to be performed.
4. Based on the system selected, All TTPs valid for that OS is displayed. User can select the TTPs to simulate and can submit.
5. Required files are then sent to the client machine with the cross-platform script used to perform simulation.
6. Supported tests are - File(Read, Write, Delete), Command Execution, Registry(Read, Write, Delete), Powershell command execution, Setting/Modifying Environment variables.
7. The result is sent back to the server and displayed on the UI.

Requirements:
Python3 - Both Client and Server Machines.

**Libraries at Client side:**
```
requests
pika
zipfile
hashlib
flask
```

**Libraries at Server side:**
```
sqlite3
requests
flask
pika
hashlib
```

