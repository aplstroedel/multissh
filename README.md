# multissh
Execute commands via ssh to multiple hosts at once

instructions:

- git clone https://github.com/aplstroedel/multissh.git
- cd ./multissh
- chmod +x ./multissh

howto:

- execute commands as normal user: ./multissh -t 'host1 host2 host3' -c 'command here'
- execute commands as root user: ./multissh -t 'host1 host2 host3' -c 'command here' -r
