# Extreme Rainfall Interpolation
This python project is intended to be used to generate estimates of extreme rainfall ranging between 1 in 2000 AEP and PMP using one of three interpolation methods:
1. A parabolic method in log-log scale as per Siriwardena & Weinmann (1998)
2. A parabolic method in log-normal scale as per Hill et al. (2000)
3. An inverse cumulative distribution function for the generalised extreme value (GEV) distribution as per Sharpe (2024)

![Extreme rainfall interpolation](https://github.com/user-attachments/assets/8a445bb2-fe58-4a31-a6e3-21960e1bc837)


# Disclaimer
There is no guarantee that the methods have been applied correctly and users should satisfy themselves that the outputs are accurate by checking the code and/or cross-checking against another calculation (like spreadsheet-based calculations).

# How to use this code
There are two python files in this project:
- ```main.py```: this is the main script and is the one that users will need to manipulate.
- ```InterpolationCurves.py```: this is the back end and is where the computations are dealt with.

The following lines of code provide the rainfall depth inputs and the estimate of the AEP of the PMP, and will need to be edited to apply the relevant details for your particular project:
```python
depth_1000 = 200
depth_2000 = 250
pmp_depth = 900
pmp_aep = 500000
```

There is also a list of AEPs that is used to produce the outputs. This may need to be adjusted (expanded or cut shorter) depending on the AEP of the PMP. The line of code that is referred to here is shown below.
```python
aeps = [1000, 2000, 5000, 10000, 20000, 50000, 100000, 200000, 500000]
```

Estimates for the three methods will then be computed for the list of AEPs shown above and output to the console. A plot of the results is also shown at the end. Users could output the estimates to a csv file by including a line at the end of the code along the lines of that shown below:
```python
df.to_csv('path to your csv file here')
```

# Required packages
The following python packages are required:
- pandas
- numpy
- matplotlib
- scipy

# References
Hill, P.I., Nathan, R.J., Rahman, A., Lee, B.C., Crowe, P. and Weinmann, P.E. (2000), Estimation of extreme design rainfalls for South Australia using the CRC-FORGE method. In: Proceedings of 3rd international hydrology and water resources symposium interactive hydrology, Engineers Australia, Perth, Western Australia, 1: 558-563, 20-23 Nov 2000

Siriwardena, L. & Weinmann, P.E. (1998). A technique to interpolate frequency curves between frequent events and probable maximum events. CRCCH Research Report 98/9, Cooperative Research Centre for Catchment Hydrology, December 1998.

Sharpe, R.G. (2024). Dealing with vertex perplexity in parabolic interpolation of design rainfall. ANCOLD conference, November 2024.
