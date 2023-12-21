# Extracting & injecting BBS

<hr>

## Automated method

[All In One BBScript Tool](https://gamebanana.com/tools/8363)

TODO: Upload generic versions of Broscar's DBFZ scripts

<hr>

## Manual method

### Bulk extracting all BBS from the game

Open the game's pak in Fmodel, and open the package search window (ctrl+shift+f). Type in `BBS_`.
Select all items in that window (ctrl+a), right click, and select 'Export Raw Data (.uasset)'.

The files will appear in the 'Output' directory, but with their original folder structure intact, which can be time consuming to work with.
To consolidize all of these BBS files, you can slap any of these scripts into your FModel directory. When you run it, it'll copy all BBS files into a single folder named 'bbs'.

TODO: Slap scripts into a github and just offer download links. Also, create a Windows batch version.

```bash
#!/bin/bash
mkdir -p "./bbs/"
for f in `find "Output" -type f -name "BBS_*"`
    do cp -f "${f}" "./bbs/"
done
```

### Extract a script from a UE4 container

### Parse the script

### Rebuild the script

### Inject the script back into the UE4 container
