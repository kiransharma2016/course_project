## useful snippets
https://awsbloglink.wordpress.com/2017/11/05/how-to-restart-the-os-with-ansible/

## how to run playbook on localhost
There are two ways to provide hosts in ansible
--command to use an inline inventory list, eg -c local -i 'localhost,' 
--put all your host in a file and give that with -i inventory file with location while running the playbook
eg

ansible-playbook -c local -i 'localhost,' playbook.yaml
