# Alternate Data Streams

![b136c7234f43e13a5bf09c635fd0c9ee.png](../../_resources/b136c7234f43e13a5bf09c635fd0c9ee.png)

Alternate Data Streams (ADS) is a feature of the **NTFS** file system in Windows that allows a file to contain multiple streams of data. Each stream has a name and the primary data stream is unnamed.

By storing data in an ADS, the content becomes less visible because typical file browsing and searching operations do not reveal the existence of ADSs.

## example

this is a demonstration of hiding a file in alternate data streams.
first, we create a `datafile.txt` file:

![d7b2837f6b9ed5b56012aae6f9638af9.png](../../_resources/d7b2837f6b9ed5b56012aae6f9638af9.png)

then, we create another file called `adsfile.txt`. the second command takes the content of adsfile.txt and writes it into an Alternate Data Stream (ADS) named hidden.txt attached to the file `datafile.txt`.

![aae787eda15e1daa94cdf17e048c7e97.png](../../_resources/aae787eda15e1daa94cdf17e048c7e97.png)

now when you open datafile.txt, there is no specific change to be recognized.

![09485b616084521656c59d6336153209.png](../../_resources/09485b616084521656c59d6336153209.png)

to retrieve the hidden message from the ADS, you would use the following command:

```shell
more < datafile.txt:hidden.txt
```
