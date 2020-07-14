# Installing Model on SCW

Here are the steps I used to get Model installed and running on Sunbird.

### Download Model

```bash

hg clone https://model@bitbucket.org/model/model Model

```

### Load Modules Required

```bash

module load boost/1.69.0
module load eigen/3.3.7
module load mkl

```

### Change Directory to Dislocation Dynamics

```bash

cd /home/s.t.d.pritchard/local_builds/Model/tutorials/DislocationDynamics

```

### Edit Makefile

Template can be seen here: https://github.com/pritchardtom/Model_Makefile/blob/master/Makefile, but you need to:

1. Change `MODEL_INCLUDE` on line 7.
2. Comment out `GREATWHITE_INCLUDE` on line 8.
3. Change `EIGEN_INCLUDE` on line 9 to point to correct location.
4. Change `MKL_INCLUDE` on line 10 to point to correct location.
5. Comment out `IDIR += -I$(GREATWHITE_INCLUDE)` on line 21.
6. Change `MKL_LIB` on line 76 to point to correct location.


### Change Directory to `uniformLoadController`

```bash

cd finiteDomains_NO_FEM/uniformLoadController/

```

### Build Instructions

```bash

make -f Makefile
make microstructureGenerator
make DDomp
./DDomp

```
