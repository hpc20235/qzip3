# qzip3 Compressor

A minimalistic implementation of [FrodoKEM](https://frodokem.org/) lattice encryption layer over a slightly improved Bzip2 compression. Inspired by https://github.com/microsoft/PQCrypto-LWEKE.

# Usage

A single file/folder (de)compression / (de)encryption is supported. 

```bash
# compression 
qzip3 -c inputFile|inputFolder [-p password] -o outputFile

# decompression
qzip3 -d achiveFile [-p password]
```

## Examples

### With encryption

```bash
# compress the file and encrypt 
qzip3 -c file.txt -p test -o file.qzip3

# decrypt and decompress
qzip3 -d file.qzip3 -p test
```

### Without encryption

Without encryption, a modified Burrows–Wheeler transform is used which can improve compression rate for small (1KB) text files.

```bash
# compress
qzip3 -c file -o file.qzip3


# decompress
qzip3 -d file.qzip3
```

**Note**

Decompression is done to the folder where the archive file is located. Not to mistakenly pollute the working directory, put the archive file into a separate folder and extract:

```bash

# The extracted files will be placed in mydir

qzip3 -d mydir/file.qzip3 
```


# Requirements 

Opam v4.1+ is required.

# Releases

Binary releases are available for Linux only.