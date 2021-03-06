# Motion correction, deconvolution and demixing of calcium imaging data

[![Join the chat at https://gitter.im/epnev/ca_source_extraction](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/epnev/ca_source_extraction?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

The code implements a method for simultaneous source extraction and spike inference from large scale calcium imaging movies. The code is suitable for the analysis of somatic imaging data. Implementation for the analysis of dendritic/axonal imaging data will be added in the future. 

The algorithm is presented in more detail in

Pnevmatikakis, E.A., Soudry, D., Gao, Y., Machado, T., Merel, J., ... & Paninski, L. (2016). Simultaneous denoising, deconvolution, and demixing of calcium imaging data. Neuron 89(2):285-299, http://dx.doi.org/10.1016/j.neuron.2015.11.037

Pnevmatikakis, E.A., Gao, Y., Soudry, D., Pfau, D., Lacefield, C., ... & Paninski, L. (2014). A structured matrix factorization framework for large scale calcium imaging data analysis. arXiv preprint arXiv:1409.2903. http://arxiv.org/abs/1409.2903

New: Motion Correction
======
We have just released [NoRMCorre](https://github.com/simonsfoundation/NoRMCorre) a new toolbox for NOn-Rigid Motion CORREction. You can find it in [Matlab](https://github.com/simonsfoundation/NoRMCorre) as a standalone package to be integrated with this package, or Python as part of [CaImAn](https://github.com/simonsfoundation/CaImAn).

Code description
=======

The best way to start is by looking at the various demos.
- [demo_script.m](https://github.com/epnev/ca_source_extraction): A simple demo with a small dataset included in the repo to display the notation and basic operations
- [demo_memmap.m](https://github.com/epnev/ca_source_extraction/blob/master/demo_memmap.m): A larger demo displaying the process of memory mapping and spliting the field of view in patches to be processed in parallel and then combined.
- [run_pipeline.m](https://github.com/epnev/ca_source_extraction/blob/master/run_pipeline.m): Demo for the complete pipeline of motion correction, source separation and spike extraction for large datasets. More details about the pipeline can be found [here](https://github.com/epnev/ca_source_extraction/wiki/Complete-analysis-pipeline).
- [3D/demo_3D.m](https://github.com/epnev/ca_source_extraction/blob/master/3D/demo_3D.m): Demo for processing of 3D volumetric imaging data.

Related packages
=======

This repository contains a MATLAB implementation of the spatio-temporal demixing, i.e., (source extraction) code for large scale calcium imaging data. Related code can be found in the following links:

# Matlab 
- [Constrained deconvolution and source extraction with CNMF (this package)](https://github.com/epnev/ca_source_extraction)
- [MCMC spike inference](https://github.com/epnev/continuous_time_ca_sampler)
- [Fast online deconvolution of calcium imaging data (OASIS)](https://github.com/zhoupc/OASIS_matlab)
- [Group LASSO initialization and spatial CNMF](https://github.com/danielso/ROI_detect)

# Python

A complete analysis pipeline including motion correction, source extraction and activity deconvolution is performed through the package [CaImAn](https://github.com/simonsfoundation/caiman) 

Usage and Documentation
=======
Check the demo scripts and the [wiki](https://github.com/epnev/ca_source_extraction/wiki) to get started.

Dependencies
========
The following matlab toolboxes are needed for the default parameter settings:

- Statistics and Machine Learning Toolbox
- Image processing toolbox

Depending on the settings the following toolboxes may also be required

- Neural networks toolbox (required for component classifier)
- Signal processing toolbox (recommended but not required)
- Parallel computing toolbox (recommended for large datasets but not required)
- Optimization toolbox (not required)

Depending on the settings the following packages may also be required

- The CVX library which can be downloaded from http://cvxr.com/cvx/download/ (after unpacking CVX open Matlab and run cvx_setup from inside the CVX directory to properly install and add CVX to the Matlab path). **CVX is no longer required**.
- SPGL1 package from https://github.com/mpf/spgl1 (for solving constrained_foopsi using SPGL1)
- Bayesian spike inference package from https://github.com/epnev/continuous_time_ca_sampler (for using the 'MCMC" deconvolution method).

Wiki
=======
Some issues are covered in the [wiki](https://github.com/epnev/ca_source_extraction/wiki). More pages will be added and suggestions are welcome.

Questions, comments, issues
=======
Please use the gitter chat room (use the button above) for questions and comments and create an issue for any bugs you might encounter.

License
=======

This program is free software; you can redistribute it and/or
modify it under the terms of the GNU General Public License
as published by the Free Software Foundation; either version 2
of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
