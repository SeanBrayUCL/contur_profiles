# Contur Profiles
This repository contains profiling data associated witht the contur toolkit https://gitlab.com/hepcedar/contur .

Each folder of the repistory focuses on profiling a single aspect of the contur model. The folders will contain at least one .png file showing a flow chart of the contur run and the proportion of time spent in each part of the code. 

Additionally each folder will contain at least one '.prof' file which contains the output from the data output from the profiler (profiler used is cPython). The best way to view these files is using snakeviz (https://jiffyclub.github.io/snakeviz/). The snakeviz documentation provides a more comprehensive overview of how to use snakeviz, but to just view the '.prof' file all that is required is that the user downloads snakeviz (run 'pip install snakeviz' in the terminal, only need to do this one), then if we take the file we want to view to be 'test.prof', navigate with your terminal working directory to where 'test.prof'is saved and run 'snakeviz test.prof'.

The contents of each file the repository are summarised below.

## Base

## Correlation

## Grid
This profile currently contains four profiles of a contur grid run. The contents of these profiles can be summarised as follows:

1. __Starting point (grid_profile.prof and .png)__ : First profile of the contur grid run before anything optimisation was attempted. Code can be found at versions of contur before this commit https://gitlab.com/hepcedar/contur/-/commit/9615203442029415d9b3409b001a5e6ec84e03ae ;

2. __First Update__ : Given by commit https://gitlab.com/hepcedar/contur/-/commit/9615203442029415d9b3409b001a5e6ec84e03ae, the update reduced the calls to _ts_to_pval by a factor of 2.

3. __Second Update__: Given by commit https://gitlab.com/hepcedar/contur/-/commit/0d15e0183b9850553dc9638dedf635163a70b3d3 and the previous commit, reduces the calls to _ts_to_pval by another factor of 2.

4. __Third Update__: Given by commit  https://gitlab.com/hepcedar/contur/-/commit/647ce7c6b3f30c86833d89cf0dd674a69bf027f1, allows _ts_to_pval to take a numpy array of values of input. This allows the scipy stats norm method called by _ts_to_pval to act on the numpy array as opposed to each array element in a seperate call. The speed up comes from the vectorisable features of the scipy method on numpy arrays.
