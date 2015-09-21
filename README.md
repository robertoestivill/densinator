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


**File extension**

```
Input files extension [PNG]:
1) PNG
2) JPG
3) JPEG
```


**Scale type**

```
Select scale type [Porcentual]:
1) Porcentual (original is considered xxhdpi)
2) Launcher icon (mipmap instead of drawable)
3) Action bar icon
4) Notification icon
```


**Generate LDPI**

```
Generate LDPI [No]:
1) No
2) Yes
```


**Output directory**

```
Enter output dir [generated/]:
```

## Example

```bash
$ tree
.
├── image1.png
└── image2.png

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

Scaling image1.png to 144x144 in output/mipmap-xxhdpi/image1.png
Scaling image1.png to 96x96 in output/mipmap-xhdpi/image1.png
Scaling image1.png to 72x72 in output/mipmap-hdpi/image1.png
Scaling image1.png to 48x48 in output/mipmap-mdpi/image1.png
Scaling image2.png to 144x144 in output/mipmap-xxhdpi/image2.png
Scaling image2.png to 96x96 in output/mipmap-xhdpi/image2.png
Scaling image2.png to 72x72 in output/mipmap-hdpi/image2.png
Scaling image2.png to 48x48 in output/mipmap-mdpi/image2.png
Done.

$ tree
.
├── image1.png
├── image2.png
└── output
    ├── mipmap-hdpi
    │   ├── image1.png
    │   └── image2.png
    ├── mipmap-mdpi
    │   ├── image1.png
    │   └── image2.png
    ├── mipmap-xhdpi
    │   ├── image1.png
    │   └── image2.png
    └── mipmap-xxhdpi
        ├── image1.png
        └── image2.png
```