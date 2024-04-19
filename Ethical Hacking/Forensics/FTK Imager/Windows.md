# Windows

let's say we have an windows image.

for example in order to solve a case, we should build an excel timeline from relavent files we find to get to the story. the excel could include columns such as file, source(mft), user, created and modified timestamps, description, ...


## MFT (master file table)

Most important file in a evidence image. without this a volume would be lost.

## Check whether a file were copied or originaly saved there

when you copy a file somewhere, the creation time changes but the modification time remains the same unless you modify the content.

**If the created time is after than modification time, it means that the file was copied there.**

## Check whether a file was downloaded from the internet

we should check the string. zoneId = 3 means from the internet.
