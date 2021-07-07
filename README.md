# PS3 ISO Utilities
[![License](https://img.shields.io/github/license/bucanero/ps3iso-utils.svg)](./LICENSE)

Fork of Estwald's PS3 ISO Tools (v 1.39) with quality-of-life improvements and features related to ODE ISOs (makeps3iso), by Zar.
Contains a few build patches by Bucanero.

**Note:** Use `--help` or `/?` as parameter to see the usage information

## makeps3iso

Usage:

    makeps3iso [options] <input> [output]

Options:

    -s, --iso_split            Split files to 4GB (.iso.0, .iso.1, ...)
    -n, --no_pup               Do not include PS3_UPDATE to the ISO.
    -r, --no_region            Do not define plain/encrypted regions. See note (2).
    -f, --use_folder_name      Use parent folder name to detect if the file is 'encrypted', see notes (3) & (4)
    -a, --align_32sectors      32 sectors (64KB) align every encrypted files, see note (3)
    -v, --verbose              Make the operation more talkative
    -h, --help                 This help text
    -i, --output_id            Includes game ID as part of output ISO name.
    
Arguments:

    <input>                    Path of an input folder, PS3 JB backup
    [output]                   Path of an output file, PS3 ISO backup

Note :

    (1) If no options and arguments are specified, it will prompt the user the input data
    (2) It doesn't really encrypt the files, even if they are inside an encrypted region
    (3) This option is ignored if --no_region is defined
    (4) If it's not defined, it uses magic number of files.
    
## extractps3iso

Usage:

| Command | Description |
| :----- | :------ |
`extractps3iso`                           | interactive console input
`extractps3iso <ISO file>`                | default destination folder
`extractps3iso <ISO file> <pathfiles>`    | use `pathfiles` as destination folder
`extractps3iso -s <ISO file>`             | split big files (FAT32)
`extractps3iso -s <ISO file> <pathfiles>` | split big files (FAT32)


## patchps3iso

Usage:

| Command | Description |
| :----- | :------ |
`patchps3iso`                       | interactive console input
`patchps3iso <ISO file>`            | default version (4.21)
`patchps3iso <ISO file> <version>`  | with version (4.21 to 4.60)

**Note:** `patchps3iso` can patch ISO split files (.iso.x or .ISO.x)

## splitps3iso

Usage:

| Command | Description |
| :----- | :------ |
`splitps3iso`                       | interactive console input
`splitps3iso <ISO file>`            | split ISO image (4Gb)
