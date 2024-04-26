Adaptive Phytoplankton Community Model

The Adaptive Phytoplankton Community Model (APCM) is an NPZD-ecosystem model for the Baltic Sea that simulates the dynamics of three common phytoplankton taxa 
(dinoflagellates, diatoms, dizotrophic cyanobacteria) under both present-day and future climate conditions. The model is implemented in 
a zero-dimensional framework and uses an agent-based approach to simulate phytoplankton life cycle dynamics and evolutionary processes. 
Phytoplankton life cycle dynamics are represented by growing and resting stages. To account for evolutionary processes, the model allows for 
two flexible temperature-dependent phytoplankton traits, cell size and optimum temperature for growth. While phytoplankton cell size can adapt 
plastically to changing temperatures, optimum temperature can change through mutation and selection. Mutations in the optimum temperature can 
be enabled or disabled to study the effect of adaptation on the phytoplankton community. Since adaptation can be affected by the resuspension 
of resting cells from the sediment, the model includes an explicit representation of this process, which can be both enabled or disabled as 
well. All code is written in MATLAB R2022a.

Currently, two releases of the model are available.

Version 1.0.0 was used for a publication in _Limnology and Oceanography_ (Hochfeld, I. and Hinners, J.: Evolutionary adaptation to steady or changing environments affects competitive outcomes in marine phytoplankton, _Limnology and Oceanography_, https://doi.org/10.1002/lno.12559, 2024).

Version 1.1.0 represents a slightly extended version of the APCM that allows to calculate different ecosystem functions such as nitrogen fixation and carbon export. This version of the model was used to write the manuscript "Phytoplankton adaptation to steady or changing environments affects marine ecosystem functioning" by I. Hochfeld and J. Hinners, which is currently submitted to _Biogeosciences_.

Please contact me (isabell.hochfeld@uni-hamburg.de) if you have any issues with downloading or running the model.
