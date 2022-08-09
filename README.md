# Python version (slower than Julia version)
* To use code:
    ```python gauss_linking.py -f TRAJ -p TOP -b BEGIN -e END -skip SKIP_FRAME -nproc NUMTHREAD```


Notes about |G|c values:
G>=1: entanglement exist (see original paper for details)

For single frame (pdb file), use single_frame.py for short and more detailed

For trajectory, run caller.py, which will automatically divided trajectory in multiple parts
and call ent_calculations for each part (multiple frames)
./run_caller.sh is perfect for short, but you need to modify the input params.

#  Julia version (prefer to use):
* requirement packages: MDToolbox, Distances
* To reduce precompute time, run pre_compile.jl to generate image and load into environment (this take so long, ~7 mins) but worth to do so. This is run only one.
Full command:  
    ```julia -J SYS_IMAGE.so -t NUM_THREADS gauss_linking.jl -f TRAJ -p TOP -b START_FRAME -e END_FRAME -s SKIP_FRAME ```

simple command:
    ```julia gauss_linking.jl -f PDBFILE```

### Note:
MDToolbox is not able to load structure contains HEATATM like ions. Find different library

## Do you want to cite this work?
Vu, Quyen. (2022). entanglement analysis. Zenodo. https://doi.org/10.5281/zenodo.6976792

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.6976792.svg)](https://doi.org/10.5281/zenodo.6976792)
