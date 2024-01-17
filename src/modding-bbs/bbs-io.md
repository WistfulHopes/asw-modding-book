# Extracting & injecting BBS

<hr>

## Automated method

[All In One BBScript Tool](https://gamebanana.com/tools/8363)

TODO: Upload generic versions of Broscar's DBFZ scripts

<hr>

## Manual method

Manually extracting and injecting scripts is preferred if other assets need to be packaged.

### Bulk extracting all BBS from the game

Open the game's pak in FModel, and open the package search window (Ctrl + Shift + F). Type in `BBS_`.
Select all items in that window (Ctrl + A), right click, and select 'Export Raw Data (.uasset)'.

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

### Extract a script from the .uasset/.uexp

Using [Pangaea's ggst-bbs-unpacker](https://github.com/super-continent/ggst-bbs-unpacker/releases/tag/0.0.1), scripts (and other ArcSys binaries) can be extracted. After exporting the .uasset from FModel, open the .uasset *and* .uexp files using ggst-bbs-unpacker. Then, click Extract and save it in a location of your choosing.

### Parse the script

Using [Pangaea's BBScript tool](https://github.com/super-continent/bbscript/releases/tag/1.0.0) by itself, you will need to use the command line. **If you have never used the command line before, find a tutorial on it first.**

In the command line, run ```cmd
bbscript parse <config> <binary> <text>
```

where <config> is the matching configuration filename in static_db, <binary> is the extracted script, and <text> is the file to parse to.

<div class="warning">

If the file to parse to already exists, an error will be thrown to prevent accidental overwriting. If you do wish to overwrite the given file, put `-o` after the command.

</div>

### Rebuild the script

The BBScript tool can also rebuild scripts from text back into binary form. 

In the command line, run ```cmd
bbscript rebuild <config> <text> <binary>
```

where <config> is the matching configuration filename in static_db, <text> is the modified text, and <binary> is the script to write to.


### Inject the script back into the .uasset/.uexp

ggst-bbs-unpacker can also inject scripts and other binaries back into the .uasset/.uexp. Open the original .uasset and .uexp. Then, select the file you wish to inject. Finally, click Inject. 