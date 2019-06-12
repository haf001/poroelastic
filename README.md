# poroelastic
Implementation of the (multicompartment) poroelastic equations.

## Installation
Poroelastic is only offered using Python 3.x.
```
python3 setup.py install
```
installs the package and its dependencies.

## Requirements

Poroelastic requires FEniCS 2017.2.0, upwards compatibility is suspected, but has not been tested. Because poroelastic requires FEniCS we recommend setting up a Docker container
using the Dockerfile
```
docker build --no-cache -t poroelastic:2017.2.0 .
```
To enter the container you can use
```
docker run -ti -p 127.0.0.1:8000:8000 -v $(pwd):/home/fenics/shared -w /home/fenics/shared "poroelastic:2017.2.0"
```
The tag reflects the FEniCS version used to develop the package.

To view the output Paraview 5.x is required.

# multi-compartment_poroelastic
The original poro-elastic python codes only functioned for single compartment scenarios where N = 1.

Some modifications have been made to the problem.py file to enable solving for multi-compartment scenarios. The updated problem.py file is uploaded here: https://github.com/haf001/multi-compartment_poroelastic

A demo_thesis.py file is uploaded to enable solving multi-compartment problems as well as a demo_thesis.cfg file.

For the Python codes listed above see: https://github.com/haf001/multi-compartment_poroelastic 

Replacing the original problem.py file with this modified version and running the demo_thesis.py file with the demo_thesis.cfg file will provide numerical solutions presented on the master thesis report.

To run the poro-elastic Python code, locate the demo_thesis.py file on the docker container using the ubuntu terminal and type: python3 demo_thesis.py --cfg ../data/demo_thesis.cfg

Hit enter.

Visualizing the numerical solution on Paraview will produce the results seen in the thesis report.
