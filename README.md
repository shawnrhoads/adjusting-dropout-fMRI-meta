# Adjusting for variable dropout in fMRI meta-analysis

This project was prompted by finding variable dropout during an fMRI meta-analysis on prosocial decision-making: Cutler, J., Campbell-Meiklejohn, D., (2018) A comparative fMRI meta-analysis of altruistic and strategic decisions to give, NeuroImage, doi: https://doi.org/10.1016/j.neuroimage.2018.09.009. To account for this, we adjusted the method used by AES:SDM meta-analysis software created by Joaquim Radua, Anton Albajes-Eizagirre and others: www.sdmproject.com, see Radua et al., (2012) A new meta-analytic method for neuroimaging studies that combines reported peak coordinates and statistical parametric maps. European Psychiatry, doi: 10.1016/j.eurpsy.2011.04.001. A paper describing the theoretical basis of this adjustment is in prep, if you have any questions please contact Jo Cutler - J.Cutler@sussex.ac.uk

The project contains:
- MATLAB code (using SPM) 'adjusting_FE_RE_and_ME.m' to run either a single group mean (random effects) or two group mean and comparison (mixed effects) meta-analysis. Fixed effects estimates are given in the process of a random effects analysis but are not recommended.
- MATLAB function code 'run_imcalc.m' used in the above analysis.
- An Excel spreadsheet 'excel_sheet_for_adjusting_1_voxel' which gives the same output as the code but for a single voxel. This can be updated to calculate for a different number of studies and their relevant effect sizes.
- 18 fMRI maps relating to decision-making tasks which can be used to run a demonstration of the code. These were downloaded from Neurovault: Gorgolewski et al., (2015) NeuroVault.org: a web-based repository for collecting and sharing unthresholded statistical maps of the brain. Front. Neuroinform. doi: 10.3389/fninf.2015.00008. Details of these files can be found in the document 'NeuroVault_studies' (Excel or text versions) and we are very grateful to the authors for making their data openly available.

# Note on proprietary software
If you are unable to use any aspect of this project due to the related software licences please contact me (J.Cutler@sussex.ac.uk) and I will try to provide alternatives. In time, I hope to provide versions which do not rely on proprietary software but wanted to share these existing versions as soon as possible.

# Demo data
These demo data were identified through searches on NeuroVault for the keywords “choice” and “deci*". This technique was used to quickly gather data which is licensed for reuse and resharing. The results of the meta-analysis generated by using these maps is in no way comprehensive or meaningful. There are 18 datafiles which were randomly allocated between two groups of 9 for the mixed effects analysis.

# Getting started using demo data
Download and unzip the repo folder into your preferred location. Run the script 'adjusting_FE_RE_and_ME.m' and select the Data directory containing all of the data files in the window that appears. These maps have already been preprocessed using AES:SDM for your convenience.

# Getting started with your own data
This script requires the first steps of a meta-analysis in AES:SDM to be run BEFORE running the adjusted analysis. Please visit www.sdmproject.com, download the software and follow the steps described up to at least the preprocessing stage.
The instructions for this will explain what types of data can be included (peaks and maps) and demonstrate how to organise the data.
You may want to run all the stages of the AES:SDM method to get the unadjusted results for your meta-analysis. These can be compared to the results from this script to check that it has worked correctly (look for the files with "All" in the name from this output to compare with AES:SDM).

IMPORTANT - AES:SDM preprocessing outputs the files as .nii.gz but this script requires .nii input. Simply select all of the files beginning "pp_" from the AES:SDM output and unzip them into the same folder. (These will be pp_(study)_var.nii.gz and pp_(study).nii.gz files.) Also unzip the file sdm_mask.nii.gz so it becomes sdm_mask.nii.

When you have done this, download the two .m files from this repo. Run the script 'adjusting_FE_RE_and_ME.m' and select the directory containing your unzipped preprocessed files as well as the sdm_table in the window that appears. As part of the ouput, a map of the coverage of the studies will be produced.

# Prerequisites
You need SPM downloaded and on the matlab path to run this script. To download SPM visit www.fil.ion.ucl.ac.uk/spm/
Follow the instructions online then add the location of SPM on your computer using the script provided (either add the path into the script or a window will open for you to select the location of SPM).

# Built with
AES:SDM v5.141 software (for initial steps - see above)

MATLAB 2017

SPM 12

on Windows 64-bit PC running Windows 7

# Contributing
As I'm new to sharing code, GitHub etc. I would appreciate any contributions or feedback on how to improve. 

# Authors
Jo Cutler - J.Cutler@sussex.ac.uk

# License
This project is licensed under the MIT License - see the LICENSE.md file for details. 

If you use the method, please cite the NeuroImage paper until the methods paper on the technique is available - https://doi.org/10.1016/j.neuroimage.2018.09.009

# Acknowledgments
This adjusted method was developed with Dan Campbell-Meiklejohn. We would like to thank Joaquim Radua and Anton Albajes-Eizagirre for their support using AES:SDM and for helpful comments on developing this method. We would also like to thank the authors who shared data on NeuroVault and the developers of that platform for enabling the sharing of data.
