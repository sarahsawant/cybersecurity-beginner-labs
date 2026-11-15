# Network Connections and Process Identification

## Aim
To explore active network connections in Windows and identify the applications associated with them.

## Tools Used
- Windows Command Prompt
- netstat
- tasklist

## Commands Performed

### 1. View Network Connections
`netstat -ano`

Displayed TCP connections, connection states and associated Process IDs (PIDs).

### 2. View Running Processes
`tasklist`

Displayed running applications and their Process IDs.

### 3. Identify a Process
`tasklist /FI "PID eq [PID]"`

Used a PID from the network connection list to identify its associated application.

### 4. Filter Network Connections
`netstat -ano | findstr [PID]`

Filtered network connections using a specific PID.

## Observation
During the experiment, I identified `mysqld.exe`, a MySQL Server process, associated with port 3306.

## Learning Outcome
I learned how to:
- View active network connections.
- Understand LISTENING and ESTABLISHED states.
- Identify applications using Process IDs.
- Connect network activity with running Windows processes.

This practical helped me understand a basic technique used in network monitoring and security investigations.
## Screenshots

### 1. Network Connections using netstat
![Netstat Output](Screenshots/05-netstat-connections.png)

### 2. MySQL Process Identification
![MySQL Process](Screenshots/06-mysql-process-identification.png)
