# Lambert-projection
Lambert conformal conic projection - two standard parallel (2SP) case. Python and Matlab implementation. Implemented according to IOGP report, page 19: http://www.epsg.org/Portals/0/373-07-2.pdf?ver=2018-10-12-153840-577
### Methods
**geographic2cartesian** &#8211; Converts geographic coordinates (latitude, longitude) to Cartesian coordinates (x, y).<br>
**cartesian2geographic** &#8211; Converts Cartesian coordinates (x, y) to geographic coordinates (latitude, longitude).<br>
*Note:* x is called "easting," y is called "northing."

## Usage
### Python
```python
lamb = Lambert(
    (standard_parallel_1, standard_parallel_2),
    central_latitude, central_longitude,
    false_easting, false_northing,
    semimajor_axis, inverse_flattening
)

x, y = lamb.geographic2cartesian(latitude, longitude)

latitude, longitude = lamb.cartesian2geographic(x, y)
```
### Matlab
```matlab
lamb = Lambert(...
    [standard_parallel_1, standard_parallel_2],  ...
    central_latitude, central_longitude,         ...
    false_easting, false_northing,               ...
    semimajor_axis, inverse_flattening           ...
);

[x, y] = lamb.geographic2cartesian(latitude, longitude);

[latitude, longitude] = lamb.cartesian2geographic(x, y);
```

## Projection Constants
Constants used in both examples ```python_implementation/lambert_test.py``` and ```matlab_implementation/lambert_test.m``` (defined in file ```projection_constants.json```) correspond to MGI / Austria Lambert 48, source: https://spatialreference.org/ref/sr-org/mgi-austria-lambert-48/html/
