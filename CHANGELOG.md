## 2015-12-08

- All output files are now `png`.
- Initial support for `svg` files.
 - Make sure `imagemagick` has been installed with `--with-librsvg`. [This link] (http://stackoverflow.com/a/27524633/961759) provides instructions on how to do this.
 - Make sure you select the output base size either by choosing one from the list, or manually entering it, otherwise the script will fail with the error `ERROR svg file found but base size was not defined`.
- Fix: open the output folder after execution.


## 2015-11-29

- Fixed issue with file names with dash characters
- Added PNG optimizations with [pngquant](https://pngquant.org/)
- LDPI resources are now always generated
- All types of resizes are now internally using percentages.
- Porcentual resize now requests the base size to use on the `xxxhdpi` resource.


## 2015-10-22

- Adding support for `xxxhdpi` which is now the baseline for porcentual resizes


## 2015-09-22

- Fixing issue with file names with blank spaces


## 2015-09-21

- Initial release