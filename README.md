Adaptive Phytoplankton Community Model

The software package contains an NPZD-ecosystem model for the Baltic Sea that simulates the dynamics of three common phytoplankton taxa 
(dinoflagellates, diatoms, dizotrophic cyanobacteria) under both present-day and future climate conditions. The model is implemented in 
a zero-dimensional framework and uses an individual-based approach to simulate phytoplankton life cycle dynamics and evolutionary processes. 
Phytoplankton life cycle dynamics are represented by growing and resting stages. To account for evolutionary processes, the model allows for 
two flexible temperature-dependent phytoplankton traits, cell size and optimum temperature for growth. While phytoplankton cell size can adapt 
plastically to changing temperatures, optimum temperature can change through mutation and selection. Mutations in the optimum temperature can 
be enabled or disabled to study the effect of adaptation on the phytoplankton community. Since adaptation can be affected by the resuspension 
of resting cells from the sediment, the model includes an explicit representation of this process, which can be both enabled or disabled as 
well. In addition to the model code, the package includes scripts to evaluate and visualize the model output. All code is written in MATLAB 
R2022a.

In the publication related to this model, six different model scenarios are evaluated:
- C (Control): present-day seasonal temperature forcing, both adaptation in the optimum temperature and resuspension are disabled
- CA (Control & Adaptation): present-day seasonal temperature forcing, adaptation is enabled and resuspension is disabled
- CAR (Control & Adaptation & Resuspension): present-day seasonal temperature forcing, both adaptation and resuspension are enabled
- W (Warming): seasonal forcing plus steady warming, both adaptation in the optimum temperature and resuspension are disabled
- WA (Warming & Adaptation): seasonal forcing plus steady warming, adaptation is enabled and resuspension is disabled
- WAR (Warming & Adaptation & Resuspension): seasonal forcing plus steady warming, both adaptation and resuspension are enabled


Description of the file structure

| - AdaptivePhytoplanktonCommunityModel.zip
| | - APCM.m                                   Main program
| | | - Functions/                             Functions required to run the main program
| | | - Evaluation/                            Scripts and directory structure for evaluation of model output
| | | | - Output_Files/                        Directory where model output files and variables from these files are stored
| | | | - Load_Files/                          Scripts to load model output and save variables required for evaluation to Output_Files/
| | | | | - load_C.m                           Script to load C model output files (present-day climate, no adaptation/resuspension)
| | | | | - load_CA.m                          Script to load CA model output files (present-day climate, adaptation, no resuspension)
| | | | | - load_CA_din.m                      Script to load CA model output files with only dinoflagellates
| | | | | - load_CA_dia.m                      Script to load CA model output files with only diatoms
| | | | | - load_CAR.m                         Script to load CAR model output files (present-day climate, adaptation, and resuspension)
| | | | | - load_W.m                           Script to load W model output files (warming climate, no adaptation/resuspension)
| | | | | - load_WA.m                          Script to load WA model output files (warming climate, adaptation, no resuspension)
| | | | | - load_WA_din.m                      Script to load WA model output files with only dinoflagellates
| | | | | - load_WA_dia.m                      Script to load WA model output files with only diatoms
| | | | | - load_WAR.m                         Script to load WAR model output files (warming climate, adaptation, and resuspension)
| | | | - Plotting_Functions/                  Directory containing plotting functions
| | | | | - Figures_Manuscript.m               Script, Figs. 2 and 3 from the manuscript, statistics, loads variables from Output_Files/
| | | | | - Figures_Supporting_Information.m   Script, Figs. S1-S12 from the Supp. Information, loads variables from Output_Files/
| | | | | - Functions/                         Functions required to run Figures_Supporting_Information.m
| | | | - Output_Plots/                        Directory where figures are saved


Workflow:

By running the main program APCM.m, an output file (.mat) is created for the current simulation and saved in Evaluation/Output_Files/. To 
extract the variables from the output file that are necessary for further evaluation, one of the scripts from Evaluation/Load_Files/ must be 
run. Which of the scripts to run depends on the model scenario the simulation belongs to (see above). For example, the output file for a CA 
simulation must be loaded with load_CA.m since it contains different variables than an output file for a C simulation. Since the model contains 
stochastic processes, e.g., mutations, it is suggested to perform multiple simulations for one model scenario and average the output. To do so, 
all output files that belong to the same scenario can be loaded simultaneously with the corresponding script to get averaged variables for 
evaluation. The variables for evaluation are saved to a separate file in Evaluation/Output_Files/. Now, the scripts from Evaluation/Plotting_Functions/ 
can be run to further evaluate and visualize the model output. While Figures_Supporting_Information.m creates figures only, Figures_Manuscript.m also 
includes statistical analyses (t test). Both scripts load the variable files from Evaluation/Output_Files/; the created figures are saved in 
Evaluation/Output_Plots/.
