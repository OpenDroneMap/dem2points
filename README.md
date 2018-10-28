# dem2points

Extract 3D points from digital elevation models

![image](https://user-images.githubusercontent.com/1951843/47622381-e08f1800-dada-11e8-8e23-1b4a37bed2ef.png)

## Dependencies

GDAL is the only dependency. To install it run:

```
sudo apt-get install -y libgdal-dev 
```

## Building

```bash
mkdir build && cd build
cmake ..
make
``` 

## Running

```bash
./dem2points -verbose -inputFile dem.tif -outputFile points.ply
```

## Disclaimer

This software is a component of OpenDroneMap. We haven't done much testing outside of its uses within OpenDroneMap so bugs may be present when testing with datasets in the "wild".

## Credits

- Command line parser library modified from https://github.com/mkazhdan/PoissonRecon
