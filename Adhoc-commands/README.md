ADHOC COMMANDS TO TRY- 

#Check hostnames -->
ansible -i inventory.ini -m shell -a "hostname" all

#Copy a file from Control node tp remote node --> 
ansible -i inventory.ini -m copy -a "src=file-to-copy-onto-instance.txt dest=/tmp/remote-file.txt"  all --become

#Install Python -->
ansible -i inventory.ini all -m apt -a "name=python3 state=present update_cache=yes" --become

#Run to verify the Python version installed
ansible -i inventory.ini all -m shell -a "python3 --version"
