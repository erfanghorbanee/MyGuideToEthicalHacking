# Tools to extract data from image

<https://infosecwriteups.com/beginners-ctf-guide-finding-hidden-data-in-images-e3be9e34ae0d>

## binwalk

-e option extracts data in the folder named “_signature-new.jpg.extracted”.

```shell
binwalk -e signature-new.jpg
```

but ”-e” option could be buggy sometimes. so we can use this instead:

```shell
binwalk --dd='.*' 05-idea.jpg 
```

to extract all of the possible files by their offset.

another way is to manually check the hex of our file, and select the part that is related to our hidden file and create a new file using that hex.

## tips

- **sometimes only changing the height or width of the image can reveal some information!**
