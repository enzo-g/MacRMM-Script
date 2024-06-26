# MacRMM-Script

This script is designed to assist users in adding Mac agents to Tactical RMM without the need for upfront payment for code-signed agents. If you find this solution beneficial, please consider contributing to the Tactical RMM project!

# rmmagent-script

Script for one-line installation and updating of the tacticalRMM agent.

> Currently, both amd64 and arm64 scripts are available; however, only the amd64 version has been tested on macOS 13 (Ventura).

Scripts for additional platforms will be developed and released as they are adapted. You are welcome to modify the script and contribute your improvements back to the project.

# Usage

Download the script that match your configuration

### Tips
Download script with this url: `https://raw.githubusercontent.com/mattchis/MacRMM-Script/main/rmmagent-mac.sh`

## Install
To install agent launch the script with this argument:

```bash
./rmmagent-mac.sh install 'System type' 'Mesh agent' 'API URL' 'Client ID' 'Site ID' 'Auth Key' 'Agent Type'
```
The compiling can be quite long, don't panic and wait few minutes... USE THE 'SINGLE QUOTES' IN ALL FIELDS!

The argument are:

2. System type

  Type of system. Can be 'amd64' 'arm64' 

3. Mesh agent

  The url given by mesh for installing new agent.
  Go to mesh.fqdn.com > Add agent > Installation Executable Linux / BSD / macOS > **Select the good system type**
  Copy **ONLY** the URL with the quote.
  
4. API URL

  Your api URL for agent communication usually https://api.fqdn.com.
  
5. Client ID

  The ID of the client in which agent will be added.
  Can be view by hovering the name of the client in the dashboard.
  
6. Site ID

  The ID of the site in which agent will be added.
  Can be view by hovering the name of the site in the dashboard.
  
7. Auth Key

  Authentication key given by dashboard by going to dashboard > Agents > Install agent (Windows) > Select manual and show
  Copy **ONLY** the key after *--auth*.
  
8. Agent Type

  Can be *server* or *workstation* and define the type of agent.
  
### Example
```bash
./rmmagent-mac.sh install amd64 "https://mesh.fqdn.com/meshagents?id=XXXXX&installflags=X&meshinstall=X" "https://api.fqdn.com" 3 1 "XXXXX" server
```

## Update
Simply launch the script that match your system with *update* as argument.

```bash
./rmmagent-mac.sh update
```

## Uninstall
To uninstall the agent, execute the script with the following argument:

```bash
./rmmagent-mac.sh uninstall
```

### WARNING
- You should **only** attempt this if the agent removal feature on TacticalRMM is not working.
- Running uninstall will **not** remove the connections from the TacticalRMM and MeshCentral Dashboard. You will need to manually remove them. It only forcefully removes the agents from your linux box.
