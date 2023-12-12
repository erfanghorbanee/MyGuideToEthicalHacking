## tips
1- A lot of courses still recommend using a "stealth scan" (-sS) to add obfuscation to Nmap... well, that has been the default activity of Nmap when running as Sudo for ages now and is pretty outdated advice. But you can make your scans a lot harder to spot by fragmenting the packets (-f) setting a custom ttl that isn't Nmap's default (-ttl 58), randomizing the hosts being scanned (--randomize-hosts), appending random data to each packet (--data-length 8), and reducing the speed of the scan (-T2). 

Put them all together like this for much more subtle scans:

 nmap -f -T2 --data-length 8 --randomize-hosts -ttl 58 [targets] 

[source](https://www.linkedin.com/posts/travis-deforge-35d_a-lot-of-courses-still-recommend-using-a-activity-7137038515288100864-7fnh?utm_source=share&utm_medium=member_desktop)

2- I find NMAP is a guaranteed detection now. The above approach definitely goes a long way. 

If you are fortunate and have internal access to a host I find it more effective to analyze traffic to identify and prioritize targets. 

This can be done with netmon.exe

That said nothing is a guarantee. host based XDR is incredibly quick at picking up patterns it doesn’t like. 

Using netmon and converting to pcap has been a winner for me. 

[source](https://www.linkedin.com/feed/update/urn:li:activity:7137038515288100864?commentUrn=urn%3Ali%3Acomment%3A%28activity%3A7137038515288100864%2C7137145021396320257%29&dashCommentUrn=urn%3Ali%3Afsd_comment%3A%287137145021396320257%2Curn%3Ali%3Aactivity%3A7137038515288100864%29)

