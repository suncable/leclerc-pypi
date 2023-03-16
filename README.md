![This is an image](https://cdn.pixabay.com/photo/2013/03/22/23/37/ferrari-96052_1280.png)

**What is Leclerc?**

Leclerc is a Sun Cable initiative that creates a PERT wrapper around levelised cost formulas to identify Monte Carlo trends in PERT inputs.
This package has derived work done by Heiko Onnen which can be found at: https://towardsdatascience.com/python-powered-monte-carlo-simulations-fc3c71b5b83f and https://towardsdatascience.com/python-scenario-analysis-modeling-expert-estimates-with-the-beta-pert-distribution-22a5e90cfa79.

**How to Install**

Running ```pip install leclerc``` will install the leclerc package. 

To download with all dependencies, run ```python3 -m pip install --upgrade --no-cache-dir --use-deprecated=legacy-resolver leclerc```


**How to Use**

To use this package, call a formula and add the parameters. For inputs that have uncertainty, apply the PERT parameter. The output should give a bokeh html showcasing a histogram of the levelised cost parameter and PDF plots for inputs. 

**Example Case for Area:**

```
@pert_monte_carlo
def rectangle_area(calculation, rectangle_name, length, height):
	return height*length
	
results = rectangle_area(
    "Area",
    "rectangle_1",
    PERT(min=1.0,mode=2.0,max=3.0, label="length"),
    PERT(min=4.0,mode=5.0,max=6.0,label="height")
)
```

**Dependencies**

Leclerc uses the following packages:

* scipy 
```pip install scipy```
* numpy
```pip install numpy```
* bokeh
```pip install bokeh```
* matplotlib
```pip install matplotlib```
