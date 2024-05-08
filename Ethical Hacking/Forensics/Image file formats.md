# Image file formats

## raw image

the output from dd acquisition is a raw image.

- it contains only the data from the source device
- all the descriptive data about the acquisition (e.g., hashes values, dates, or times) need to be saved in a separate file.

## embedded image

an embedded image contains data from the source device and additional descriptive data (metadata)

- Expert Witness Format
- Advanced Forensic Format

## Expert Witness Format

standard for forensic analysis but it has a proprietary format (compatibility is achieved through reverse engineering)

- supported by mainstream open source and commercial analysis software
- include metadata (although limited) in the acquired image:
○ date/time of acquisition
○ examiner name
○ extra notes
○ password
○ MD5 hash of the entire image
- supports image compression
- search within the acquired image
- images can be split and mounted on-the-fly

### libewf

Joachim Metz (Google) created the libewf project, open source (https://github.com/libyal/libewf, apt
install ewf-tools). It provides a library and set of tools to manage the ewf format.

- ewfacquire: reads storage media data from devices and write files to EWF files.
- ewfexport: exports storage media data in EWF files to (split) RAW format or a specific version of EWF files.
- ewfinfo: shows the metadata in EWF files.
- ewfmount: FUSE mounts EWF files.
- ewfrecover: special variant of ewfexport to create a new set of EWF files from a corrupt set.
- ewfverify: verifies the storage media data in EWF files.
