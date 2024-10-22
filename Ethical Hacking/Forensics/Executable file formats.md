# Executable file formats

## ELF (Unix-like systems, e.g., Linux)

**ELF** is the standard format used for executables, object code, shared libraries, and core dumps in Unix-like operating systems.
It is highly flexible and supports dynamic linking, making it easier to load libraries at runtime.

ELF files are divided into sections and segments. Sections are primarily for the linker (e.g., .text, .data), while segments (program headers) are for the loader.

## PE (Windows)

**PE** is the standard format for executables, DLLs, and object code in the Windows operating system.

The PE format is derived from Microsoft's Common Object File Format (COFF) and includes various sections like .text, .data, .rdata.

It supports dynamic linking (using DLLs) and is more tightly coupled with the Windows OS's memory management and execution mechanisms.
