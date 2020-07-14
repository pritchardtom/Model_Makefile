# Installing Model on SCW

Here are the steps I used to get Model installed and running on Sunbird.

## Download Model

```bash

hg clone https://model@bitbucket.org/model/model Model

```

## Load Modules Required

```bash

module load boost/1.69.0
module load eigen/3.3.7
module load mkl

```

## Change Directory to Dislocation Dynamics

```bash

cd /home/s.t.d.pritchard/local_builds/Model/tutorials/DislocationDynamics

```



edit Makefile
cd finiteDomains_NO_FEM/uniformLoadController/

make -f Makefile
make microstructureGenerator
make DDomp
./DDomp
