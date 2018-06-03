# Computational Economics with Python

## Graduate Mini Course at Tinbergen Institute


* Primary instructor: John Stachurski
* Assistant instructor: Natasha Watkins
* Dates: 4th--7th June
* Class times: 9am--12 noon
* Location: TBA

[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/jstac/tinbergen_mini_course.git/master)

### Summary

This mini course will provide a fast paced introduction to Python for
computational economic modeling, from basic scripting to high performance
computing.  The course is aimed at graduate students with proficiency in at
least one scientific computing platform (e.g, MATLAB, Fortran, STATA, R, C or
Julia).

No Python knowledge is assumed.  

### Schedule


#### Day 1

* Python vs MATLAB vs Julia vs Fortran vs others
* The Python language: syntax and semantics
* [Jupyter notebooks](http://jupyter.org/)
* Object oriented vs procedural programming

#### Day 2

* The major scientific libraries ( [SciPy](http://www.scipy.org/) / NumPy / [Matplotlib](http://matplotlib.org/) / etc.)
* [Numba](http://numba.pydata.org/) and other JIT compilers
* Parallelization
* Distributed and cloud computing
* Application I: Inventory dynamics


#### Day 3

* Application II: Inequality and distributions
* Application III: Job search
* Application IV: Optimal savings 


#### Day 4

* The [pandas](https://pandas.pydata.org/) data analysis library
* Working with data
* Some empirical applications



### Links:

* [QuantEcon lectures](https://lectures.quantecon.org/)
* [Cheatsheets](https://cheatsheets.quantecon.org/)
* [Anaconda](https://www.anaconda.com/)
* [AWS](https://aws.amazon.com/)
* [Accessing AWS via SSH](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)



### Notes on AWS


#### To get an instance running

1. Login to Amazon AWS Console 
2. Navigate to EC2 Service
3. Choose your region for setting up an instance
6. Create security key-pair for the region if you don't have one
4. Launch & Configure an instance and choose Ubuntu 64-bit
5. enable access through Port 8000 (in addition to Port 22 for ssh)
6. Choose security key you've set up

#### Connecting and set up 

Use `ssh -i /path/to/pem-key ubuntu@hostname`

Here `hostname` is your Public DNS, as shown in the instance information from AWS console

Now run `sudo apt-get update` so you can install things you might need using `apt-get`


#### Configure instance to run Jupyter

1. ssh into the running instance using IP from AWS Console
2. Install Anaconda using wget and the latest download link for python36
3. Run: jupyter notebook --generate-config
4. For Automatic Password Setup run: jupyter notebook password
5. Edit .jupyter/jupyter_notebook_config.py and set the following

```
# Set ip to '*' to bind on all interfaces (ips) for the public server
c.NotebookApp.ip = '*'
c.NotebookApp.open_browser = False
c.NotebookApp.port = 8000
```


