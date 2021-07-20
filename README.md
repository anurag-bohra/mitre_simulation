# mitre_simulation
Client-Server Framework to simulate MITRE techniques. 

INFO:
OS Supported - Windows, OS X, Linux Based OS(Ubuntu tested)

WorkFlow:
1. Run start.py which enables a UI interface.
2. Upon executing client script at Client machine, it tries to communicate with the server to send status payload. This payload contains info such as IP, MAC, Platform, Architecture, Script status, simulation script existence, Version, etc. This payload is sent every 2 minutes and the info is updated in the database present at server's side. Payload is sent using rabbitmq to ensure that multiple clients can communicate easily with the server.
3. When administrator chooses to simulate TTPs on any client, a list containing selected TTPs is sent to the client machine, also, the required platform agent script is sent if not already present to carry on the execution of the tasks.
4. TTP specific binaries/scripts are fetched from the server machine using the REST API. 
5. For user specific TTPs, both Admin/User accounts are tried if present.
6. The result of the task is conveyed back to the server machine which is then displayed on UI with short summary.

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

