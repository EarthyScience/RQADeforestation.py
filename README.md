# RQADeforestation.py

Python bindings for the Julia package [RQADeforestation.jl](https://github.com/EarthyScience/RQADeforestation.jl/).
It provides functions for fast recurrence quantification analysis (RQA), accelerated using Julia.
This library is part of the [FAIRSenDD project](https://github.com/EarthyScience/FAIRSenDD) that utilize Sentinel-1 data for FAIR deforestation detection.

## Get Started

Install:

```sh
pip install git+https://github.com/EarthyScience/RQADeforestation.py
```

Run RQA analysis on a single time series:

```python
from rqadeforestation import rqatrend
import numpy as np

x = np.arange(1, 30, step=0.01)
y = np.sin(x) + 0.1 * x + np.random.rand(len(x))
rqatrend(y, 0.5, 10, 1)
# -0.12493604680482838
```

## Motivation

Analyzing high resolution sattelite images at global scale requires to optimize the execution efficiency.
Python is required for most openEO workflows in which performance critical parts of the code are written in a compiled programming language.
Usually, this is done in C, e.g., array operations in numpy.
Julia provides an alternative to accellerate code using a more user-friendly language.

## Citation

F. Cremer, M. Urbazaev, J. Cortés, J. Truckenbrodt, C. Schmullius and C. Thiel, "Potential of Recurrence Metrics from Sentinel-1 Time Series for Deforestation Mapping," in IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, vol. 13, pp. 5233-5240, 2020, doi: [10.1109/JSTARS.2020.3019333](https://dx.doi.org/10.1109/JSTARS.2020.3019333).

## Funding

<img src="https://github.com/EarthyScience/FAIRSenDD/raw/main/website/docs/public/ESA_logo.svg" align="left" height="50px"/>
<img src="https://github.com/EarthyScience/FAIRSenDD/raw/main/website/docs/public/ESA_NoR_logo.svg" align="left" height="50px" style="filter: contrast(0);"/>

This project was funded by the European Space Agency in the Science Result Long-Term Availability & Reusability Demonstrator Initiative.
In addition, this project was supported by the ESA Network of Resources.
