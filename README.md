# Pore microstructural and flow modelling of rocks.
### The combined workflow.

Lead Invsestigator: Olubukola Ishola (olubukola.ishola@okstate.edu)\
Co-Investigator: Javier Vilcaez

Paper 1: Statistical and neural network analysis of the relationship between the stochastic nature of pore connectivity and flow properties of heterogeneous rocks.\
DOI: https://doi.org/10.1016/j.jngse.2022.104719

Paper 2: Machine learning modeling of permeability in 3D heterogeneous porous media using a novel stochastic pore-scale simulation approach.\
DOI: https://doi.org/10.1016/j.fuel.2022.124044

Paper 3: Augmenting Xray micro-CT data with MICP data for high resolution pore-microstructural and flow modelling of carbonate rocks.\
DOI:

The order of the codes to run to implement the workflow for the project is itemized below:

Step One: [PorousMedia/micp_to_eptr: The notebook shows the principle behind the minimum incremental pore volume (MIPV) and estimating the effective pore-throat radius (EPTR) as outlined in steps in the paper above. (github.com)](https://github.com/PorousMedia/micp_to_eptr)

Step Two: [PorousMedia/xray_to_pore_size_distribution: The notebook demonstrates the workflow for obtaining pore size distribution from binarized micro-CT images. The general principle involves identifying each pore, estimating the volume of each pore, and ultimately determining the radius of a sphere with an equivalent volume of each pore. (github.com)](https://github.com/PorousMedia/xray_to_pore_size_distribution)

Step Three: You have to make a combined csv file, see sample here: [sample_b · GitHub](https://github.com/PorousMedia/stochastic_pore_microstructural_generator/blob/main/Data/sample_b.csv)\
a.	The file contains four columns with the following information: pore body radius (in microns), frequency, porosity (in percent), and representative pore-throat size.\
b.	The first column represents the output obtained from Step Two.\
c.	The frequency in the second column is expected to be one for all entries, given the way the code in Step Two identifies individual pores.\
d.	Column Three represents the porosity obtained for the sample, expressed as a percentage.\
e.	Column Four contains the representative pore-throat size obtained from Step One.\

Step Four: [PorousMedia/stochastic_pore_microstructural_generator: This code creates CSV files for pore bodies and pore throats of stochastically generated 3D pore microsturtures. The files are intended to make 3D images/ surface files and run simulations in STAR-CCM+. (github.com)](https://github.com/PorousMedia/stochastic_pore_microstructural_generator)

Step Five: [PorousMedia/star_ccm_flow_simulator: This STAR CCM+ java code takes in two csv files (pore bodies and pore throats), use them to generate pore microstructures, and simulate fluid flow through it. The output of this script is a csv file of flow properties through a set number of iterations. (github.com)](https://github.com/PorousMedia/star_ccm_flow_simulator)

Step Six: Post process outputs as needed.
