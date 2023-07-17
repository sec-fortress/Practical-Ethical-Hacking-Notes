
## Nothing Much//, Just a simple ip sweep scanner that performs multiple ICMP echo request on a network

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

**_Frequently Asked Questions:_**

**Question**: My bash script is producing an error with “seq”. How do I resolve?

**Resolution**: ```Ensure use of backtick (`) instead of using single quote ('). Alternatively, use $(seq 1 254) instead of seq```
