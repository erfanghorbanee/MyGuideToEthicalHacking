# tcpdump

The Tcpdump tool and its `libpcap` library are written in C and C++ and were released for Unix-like systems. it was ported to MS Windows as `winpcap`.

## Network Interface

Specify which network interface to listen to using `-i INTERFACE`. You can choose to listen on all available interfaces using `-i any`.  you can find available interfaces to choose from using `ip a s`.

## Save packets to file

use `-w FILE` with `.pcap` extension. you can open the file later using wireshark.

## Limit

You can specify the number of packets to capture by using `-c COUNT`. Otherwise, the packet capture will continue till you interrupt it.

## Summary

| Command                    | Explanation                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| `tcpdump -i INTERFACE`     | Captures packets on a specific network interface                            |
| `tcpdump -w FILE`          | Writes captured packets to a file                                           |
| `tcpdump -r FILE`          | Reads captured packets from a file                                          |
| `tcpdump -c COUNT`         | Captures a specific number of packets                                       |
| `tcpdump -n`               | Don’t resolve IP addresses                                                  |
| `tcpdump -nn`              | Don’t resolve IP addresses and don’t resolve protocol numbers               |
| `tcpdump -v`               | Verbose display; verbosity can be increased with `-vv` and `-vvv`           |
