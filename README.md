# Instructions for using ansible in linux via WSL 2 to Ubuntu


1. Install for updates via “sudo apt install update”
2. Install for upgrades via “sudo apt install upgrade”
3. Install git “sudo apt install git”
4. Install net-tools for typing “sudo apt install net-tools”
5. Install ansible “sudo apt install ansible”
6. Create Directory for Ansible “mkdir <folder name>”
7. Check for IP address “ifconfig”
8. To connect to other device remotely you need to type 
“ssh <username>@<ip-address>”
9. To check ssh connections type “ls -la .ssh”
10. If you want to see the content inside “cat <filename.filetype>”


# Preparing for automatically connection with passphrase
   1. Create ssh key using ed25519 “ssh-keygen -t ed25519 -C <ssh keyname>”
Give name to the ssh key
Create your preferred paraphrase
   2. Copy ssh to another machine using 
“ssh-copy-id -i ~/.ssh/id_ed25519.pub <username>@<ip-address>”
   3. Create repo on github and clone it locally to upload files from local to remote
   4. Create an inventory file “touch inventory” and store the IPs of every server.
  
   5. To see the ssh key public type “cat .ssh/id_ed25519.pub”
   6. To check the ping of every server
“ansible all --key-file ~/.ssh/ansible -i inventory -m ping”
   7. Add ssh-agent “eval $(ssh-agent)”
   8. Add “ssh-add”
   9. If you are lazy create an alias type “alias ssha='eval $(ssh-agent) && ssh-add' ”