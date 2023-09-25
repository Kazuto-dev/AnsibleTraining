
# Setting Up Ansible for Linux via WSL 2 on Ubuntu
*********************************************************

*********************************************************

*********************************************************

# Step 1: Update and Install Dependencies

Update package information:
 Run sudo apt update.

Upgrade packages (optional but recommended):
 Run sudo apt upgrade.

Install Git:
 Run sudo apt install git.

Install net-tools (for ifconfig):
 Run sudo apt install net-tools.

Install Ansible:
 Run sudo apt install ansible.

# Step 2: Prepare SSH for Remote Connections

Create a directory for Ansible (replace <directory_name> with your preferred name):
 Run mkdir <directory_name>.

Check your IP address:
 Run ifconfig.

Connect to another device remotely via SSH:
 Run ssh <username>@<remote_ip>.

List SSH connections:
 Run ls -la ~/.ssh.

View the content of a file:
 Run cat <filename.filetype>.

# Step 3: Prepare SSH Key for Automation

Create an SSH key using ed25519 (provide a name and passphrase when prompted):
 Run ssh-keygen -t ed25519 -C "<comment>".

Copy the SSH key to another machine for passwordless authentication:
 Run ssh-copy-id -i ~/.ssh/id_ed25519.pub <username>@<remote_ip>.

# Step 4: Manage Ansible Inventory and Ping Servers

Create a repository on GitHub and clone it locally for file management.

Create an inventory file and store the IPs of every server: 
 Run touch inventory.

To view the SSH key's public part:
 Run cat ~/.ssh/id_ed25519.pub.

Check the ping of every server using Ansible:
 Run ansible all --key-file ~/.ssh/id_ed25519 -i inventory -m ping.

# Step 5: Manage SSH Agent (Optional)

Add the SSH agent:
 Run eval $(ssh-agent).

Add your SSH key to the agent (if not added automatically):
 Run ssh-add.

Create an alias for convenience (optional):
 Run alias ssha='eval $(ssh-agent) && ssh-add'.
