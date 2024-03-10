# ipsweep

we can ping and find the devices that are connected to our network using this script.

```bash
#!/bin/bash

if [ "$1" == "" ]
then
echo "You forgot an IP address!"
echo "Syntax: ./ipsweep.sh 192.168.1"

else
  for ip in `seq 1 254`; do
    ping -c 1 $1.$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d ":" &
  done
fi
```

## Tips

- using `&` instead of `;` at the end of the ping command make the script faster.
- we have to run `chmode +x {filename}` on the script file to make it executable first.
- we can give it to nmap using a for loop to scan every ip included in the result.(an example of automating stuff using bash scripts)
