# Content Encoding

Data transferred in HTTP requests and responses isn’t always transmitted  
in the form of plain old text. Websites often encode their messages in different ways to prevent data corruption.  
Data encoding is used as a way to transfer binary data reliably across  
machines that have limited support for different content types. Characters  
used for encoding are common characters not used as controlled characters  
in internet protocols.

<ins>So when you encode content using common encoding schemes, you can be confident that your data is going to arrive at its destination uncorrupted. In contrast, when you transfer your data in its original state, the data might be screwed up when internet protocols misinterpret special characters in the message.</ins>

**Base64 encoding** is one of the most common ways of encoding data. It’s  
often used to transport images and encrypted information within web mes-  
sages.