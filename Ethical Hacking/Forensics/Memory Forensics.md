# Memory Forensics

Memory forensics, also known as volatile memory analysis or random access memory (RAM) forensics, is a branch of digital forensics. It involves the examination and analysis of a computer's volatile memory (RAM) to uncover digital evidence and artefacts related to computer security incidents, cybercrimes, and other forensic investigations. This differs from hard disk forensics, where all files on the disk can be recovered and then studied. Memory forensics focuses on the programs that were running when the memory dump was created. This type of data is volatile because it will be deleted when the computer is turned off.

## Volatile Data

In computer forensics, volatile data refers to information that is temporarily stored in a computer's memory (RAM) and can be easily lost or altered when the computer is powered off or restarted. Volatile data is crucial for digital investigators because it provides a snapshot of the computer's state at the time of an incident. Any incident responder should be aware of what volatile data is. The reason is that when looking into a device that has been compromised, an initial reaction might be to turn off the device to contain the threat.

Volatile data is not written to disk and is constantly changing in memory. The issue here is that any malware will be running in memory, meaning that any network connections and running processes that spawned from the malware will be lost. Powering down the device means valuable evidence will be destroyed.

## Memory Dump

A memory dump is a snapshot of memory that has been captured to perform memory analysis. It will contain data relating to running processes captured when the memory dump was created.

## Benefits of Memory Forensics

Memory forensics offers valuable benefits in digital investigations by capturing real-time data from a computer's volatile memory. It provides rapid insight into ongoing activities, detects stealthy threats, captures volatile data like passwords, and allows investigators to understand user actions and system states during incidents - all without altering the target system. In other words, memory forensics helps confirm malicious actors' activities by analysing a computer system's volatile memory to uncover evidence of unauthorised or malicious actions. It provides crucial insights into the attacker's tactics, techniques, and potential indicators of compromise (IOC).

Another thing to keep in mind is that capturing a hard disk image of a device can be time-consuming. Then, you have to consider the problem of transferring the image, which could be hundreds of gigabytes in size – and that's before you even consider how long the analysis will take the incident response (IR) team. This is where memory analysis can really help the IR team; capturing a memory dump from any device will be much faster and smaller. Suppose we prioritise RAM over a hard disk image. In that case, the IR team can already start analysing the memory dump for IOCs while beginning the process of capturing an image of the hard drive.

## Processes

A process is an independent, self-contained unit of execution within an operating system that consists of its own program code, data, memory space, and system resources. Imagine your computer as a busy chef in a kitchen. The chef can cook multiple dishes simultaneously, but to keep things organised, they use separate cooking stations for different tasks. Each cooking station has its own ingredients, pots, and pans. These cooking stations represent what we call "processes" in a computer. This is crucial in memory forensics because knowing the processes that were running during the capture of the memory dump will tell us what programs were also running at that time.

## Volatility

Volatility is a command-line tool that lets digital forensics and incident response teams analyse a memory dump in order to perform memory analysis. Volatility is written in Python, and it can analyse snapshots taken from Linux, Mac OS, and Windows. Volatility has a wide range of use cases, including the following:

- Listing any active and closed network connections
- Listing a device's running processes at the time of capture
- Listing possible command line history values
- Extracting possible malicious processes for further analysis
