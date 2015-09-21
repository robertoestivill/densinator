# Densinator

Densinator is a Bash script, that scans your current directory looking for image files, and generates the drawables for all Android densities.


Densinator requires [ImageMagick](http://www.imagemagick.org/script/binary-releases.php) to be installed and correctly configured. 

## Get the script

```
$ git clone https://github.com/robertoestivill/densinator
$ cd densinator
```

or download from [here.](https://raw.githubusercontent.com/robertoestivill/densinator/master/densinator)


Make sure the script is executable

```bash
$ chmod +x densinator
```

## Inputs


### File extension

```
Input files extension [PNG]:
1) PNG
2) JPG
3) JPEG
```


### Scale type

```
Select scale type [Porcentual]:
1) Porcentual (original is considered xxhdpi)
2) Launcher icon (mipmap instead of drawable)
3) Action bar icon
4) Notification icon
```


### Generate LDPI

```
Generate LDPI [No]:
1) No
2) Yes
```


### Output directory

```
Enter output dir [generated/]:
```

## Example

```bash
$ tree
.
├── 1.png
└── 2.png


$ densinator
Input files extension [PNG]:
1) PNG
2) JPG
3) JPEG
1

Select scale type [Porcentual]:
1) Porcentual
2) Launcher icon
3) Action bar icon
4) Notification icon
2

Generate LDPI [No]:
1) No
2) Yes
1

Enter output dir [generated/]:
output
Scaling 1.png to 144x144 in output/mipmap-xxhdpi/1.png
Scaling 1.png to 96x96 in output/mipmap-xhdpi/1.png
Scaling 1.png to 72x72 in output/mipmap-hdpi/1.png
Scaling 1.png to 48x48 in output/mipmap-mdpi/1.png
Scaling 2.png to 144x144 in output/mipmap-xxhdpi/2.png
Scaling 2.png to 96x96 in output/mipmap-xhdpi/2.png
Scaling 2.png to 72x72 in output/mipmap-hdpi/2.png
Scaling 2.png to 48x48 in output/mipmap-mdpi/2.png
Done.

$ tree
.
├── 1.png
├── 2.png
└── output
    ├── mipmap-hdpi
    │   ├── 1.png
    │   └── 2.png
    ├── mipmap-mdpi
    │   ├── 1.png
    │   └── 2.png
    ├── mipmap-xhdpi
    │   ├── 1.png
    │   └── 2.png
    └── mipmap-xxhdpi
        ├── 1.png
        └── 2.png
```