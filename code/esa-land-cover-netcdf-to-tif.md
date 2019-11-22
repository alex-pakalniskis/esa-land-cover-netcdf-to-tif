Make a new directory to store all the data

```console
neo@matrix:~$ mkdir ~/data/esa-annual-land-cover-2016-2018/
```
Change into the new directory

```console
neo@matrix:~$ cd ~/data/esa-annual-land-cover-2016-2018/
```

Download the zipped netCDF file from Copernicus Climate Change Service Climate Data Store into the folder: https://cds.climate.copernicus.eu/cdsapp#!/dataset/satellite-land-cover?tab=overview

Extract the files

```console
neo@matrix:~$ unzip ~/data/esa-annual-land-cover-2016-2018/ESACCI-LC-L4-LCCS-Map-300m-P1Y-1992_2015-v2.0.7.zip
```

Convert extracted netCDF files to TIF files for 2016

```console
neo@matrix:~$ gdalwarp -of Gtiff -co COMPRESS=LZW -co TILED=YES -ot Byte -te -180.0000000 -90.0000000 180.0000000 90.0000000 -tr 0.002777777777778 0.002777777777778 -t_srs EPSG:4326 NETCDF:C3S-LC-L4-LCCS-Map-300m-P1Y-2016-v2.1.1.nc:lccs_class C3S-LC-L4-LCCS-Map-300m-P1Y-2016-v2.1.1.tif
```

2017

```console
neo@matrix:~$ gdalwarp -of Gtiff -co COMPRESS=LZW -co TILED=YES -ot Byte -te -180.0000000 -90.0000000 180.0000000 90.0000000 -tr 0.002777777777778 0.002777777777778 -t_srs EPSG:4326 NETCDF:C3S-LC-L4-LCCS-Map-300m-P1Y-2017-v2.1.1.nc:lccs_class C3S-LC-L4-LCCS-Map-300m-P1Y-2017-v2.1.1.tif```
```

and 2018

```console
neo@matrix:~$ gdalwarp -of Gtiff -co COMPRESS=LZW -co TILED=YES -ot Byte -te -180.0000000 -90.0000000 180.0000000 90.0000000 -tr 0.002777777777778 0.002777777777778 -t_srs EPSG:4326 NETCDF:C3S-LC-L4-LCCS-Map-300m-P1Y-2018-v2.1.1.nc:lccs_class C3S-LC-L4-LCCS-Map-300m-P1Y-2018-v2.1.1.tif

```
