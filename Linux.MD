## linux network, iit 
https://nptel.ac.in/courses/117106113/5

## gluster FS
http://yallalabs.com/linux/how-to-create-a-replicated-glusterfs-volumes/

## checking the status /exit status of last command


if [[ "${?}" -ne 0 ]]; then
   echo "The command was not successful"
   exit 1
fi
