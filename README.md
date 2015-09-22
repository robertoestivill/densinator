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

0 directories, 2 files
```

```
$ densinator
Select file [ALL]:
1) image1.png
2) image2.png
3) All

Select scale type [Porcentual]:
1) Porcentual
2) Launcher icon
3) Action bar icon
4) Notification icon

Generate LDPI [No]:
1) No
2) Yes

Enter output dir [generated/]:

Scaling image1.png to 100% in generated/drawable-xxhdpi/image1.png
Scaling image1.png to 66.6% in generated/drawable-xhdpi/image1.png
Scaling image1.png to 50% in generated/drawable-hdpi/image1.png
Scaling image1.png to 33.3% in generated/drawable-mdpi/image1.png

Scaling image2.png to 100% in generated/drawable-xxhdpi/image2.png
Scaling image2.png to 66.6% in generated/drawable-xhdpi/image2.png
Scaling image2.png to 50% in generated/drawable-hdpi/image2.png
Scaling image2.png to 33.3% in generated/drawable-mdpi/image2.png

Done.
```
```
$ tree
.
├── generated
│   ├── drawable-hdpi
│   │   ├── image1.png
│   │   └── image2.png
│   ├── drawable-mdpi
│   │   ├── image1.png
│   │   └── image2.png
│   ├── drawable-xhdpi
│   │   ├── image1.png
│   │   └── image2.png
│   └── drawable-xxhdpi
│       ├── image1.png
│       └── image2.png
├── image1.png
└── image2.png

5 directories, 10 files
```