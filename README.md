# QZIP2 Compressor

A minimalistic implementation of [FrodoKEM](https://frodokem.org/) lattice encryption layer over a slightly improved Bzip2 compression. Inspired by https://github.com/microsoft/PQCrypto-LWEKE.

# Usage

A single file/folder (de)compression / (de)encryption is supported. 

```bash
# compression 
qzip2 -c inputFile|inputFolder [-p password] -o outputFile

# decompression
qzip2 -d achiveFile [-p password]
```

## Examples

### With encryption

```bash
# compress the file and encrypt 
qzip2 -c file.txt -p test -o file.qzip2

# decrypt and decompress
qzip2 -d file.qzip2 -p test
```

### Without encryption

Without encryption, a modified Burrows–Wheeler transform is used which can improve compression rate for small (1KB) text files.

```bash
# compress
qzip2 -c file -o file.qzip2


# decompress
qzip2 -d file.qzip2
```

**Note**

Decompression is done to the folder where the archive file is located. Not to mistakenly pollute the working directory, put the archive file into a separate folder and extract:

```bash

# The extracted files will be placed in mydir

qzip2 -d mydir/file.qzip2 
```


# Requirements 

Opam v4.1+ is required.

# Releases

Binary releases are available for Linux only.