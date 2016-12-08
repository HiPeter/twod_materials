[![Build Status](https://travis-ci.org/ashtonmv/twod_materials.svg?branch=master)](https://travis-ci.org/ashtonmv/twod_materials)
[![Coverage](https://codecov.io/gh/ashtonmv/twod_materials/coverage.svg?branch=master)](https://codecov.io/gh/ashtonmv/twod_materials)

# twod_materials
Python modules for high-throughput 2D Materials Characterization

# Setup
Edit config.yaml with your system's settings, following the template:

```
mp_api: your_materials_project_api_key
normal_binary: path_to_normal_vasp_executable
twod_binary: path_to_twod_vasp_executable
potentials: path_to_your_vasp_potentials
queue_system: slurm_or_pbs
```

# Usage

This package is designed to characterize 2D materials with as little
*a priori* knowledge as possible. The only input required are the
structures of the materials, which should be stored as POSCAR files in
uniquely named directories, e.g.:

+ My_2D_Search
    + WSe2
        + POSCAR
    + MoS2
        + POSCAR
    + Ti2CO2
        + POSCAR

In almost all cases, before doing anything else, the user should use the
relax() function to optimize the structures of the 2D materials using
the framework of input parameters included here.

Certain modules in the `analysis.py` files have been designed to be
sensitive to the directory structure, and will work best if you've
used the corresponding modules in the `startup.py` files to run the
calculations. Please take this into consideration.)

See the examples folder for some sample usage and workflows.
