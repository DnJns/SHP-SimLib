# SHP-SimLib. A library of solar and heat pump subsystem simulation models in TRNSYS.

`SHP-SimLib` is a model library of solar and heat pump subsystem simulation models in TRNSYS developed within the PhD thesis *Model-based Analysis of Solar and Heat Pump Systems for the Energy Supply of Residential Buildings* (Jonas, 2023).

## License
See the [LICENSE](LICENSE) file for license rights and limitations (MIT).

## Basic idea
`SHP-SimLib` is a compilation of TRNSYS subsystem models for the simulation of solar and heat pump systems in TRNSYS and is based on the PhD thesis *Model-based Analysis of Solar and Heat Pump Systems for the Energy Supply of Residential Buildings* (Jonas, 2023), with some minor modifications. 
The following TRNSYS subsystem models are available:
* Heat Pump and Heat Source Circuit - Air Source Heat Pump (ASHP)
* Heat Pump and Heat Source Circuit - Ground Source Heat Pump (GSHP)
* Heat Pump and Heat Source Circuit - Solar thermal and Ice storage Source Heat Pump (SISHP) 
* Parallel Solar Thermal Circuit
* Photovoltaic Battery System
* Solar Thermal and Heat Pump (STHP) System Control - Buffer Storage Charging by the Heat Pump 
* Solar Thermal and Heat Pump (STHP) System Control - Buffer Storage Charging by the Solar Thermal Circuit 
* Solar Thermal and Heat Pump (STHP) System Control - Ice Storage Charging by the Solar Thermal Source Circuit
* Building Energy Management System (BEMS) Control.


![](Figures/TRNSYS_Model.png) 
Fig. 1. TRNSYS subsystem models. 

The subsystems can be combined with each other and with an individual building model (including components like a buffer storage) for the different simulation studies of SHP systems and can be connected via TRNSYS equation blocks (cf. Fig. 1). The equation blocks are used as inputs and outputs of the subsystems and are connected via variables (cf. (Kuethe et al., 2008)), whereas some inputs are directly connected to the used TRNSYS Types via the defined variables. Additionally, the equation blocks are used for the definition of required calculations and variables which are used as parameters in the TRNSYS Types. Furthermore, some main model parameters and settings can be defined in the control card of the TRNSYS Simulation Studio as equations or constants.

Every system model consists of the individual building model and the subsystem `Heat Pump and Heat Source Circuit` (GSHP, ASHP or SISHP model). If a buffer storage is used, the subsystem `STHP System Control - Buffer Storage Charging by the Heat Pump` can be used for the rule-based control (RBC) of the heat pump. Furthermore, simulation models of systems with parallel integration of a solar thermal circuit contain the subsystem `Parallel Solar Thermal Circuit`. If a buffer storage is used, the subsystem `STHP System Control - Buffer Storage Charging by the Solar Thermal Circuit` can be used as RBC for the solar thermal circuit. For systems with ice storage (SISHP model), the subsystem `STHP System Control - Ice Storage Charging by the Solar Thermal Source Circuit` can be used as RBC for the ice storage charging. In case of SHP systems with PV or PVT integration, the subsystem `Photovoltaic Battery System` is additionally part of the system model, whereas the subsystem `BEMS Control` includes a Building Energy Management System for the simulation. In case of SHP systems with PVT integration, the subsystem `Photovoltaic Battery System` is used for the electrical part of the PVT collector and the thermal part of the PVT collector in the subsystems `Heat Pump and Heat Source Circuit - SISHP` or `Parallel Solar Thermal Circuit` can be linked via a two-node model approach with internal heat transfer coefficient. For further details including descriptions of the used models see (Jonas, 2023).

The folder `add_data` contains additional data for the subsystem models with example files for air/water (AW_10) and brine/water (BW_10) heat pump models (Type 401) as well as electrical load profiles for the locations Strasbourg, Athens and Helsinki.


## References
Jonas, D., 2023. Model-based Analysis of Solar and Heat Pump Systems for the Energy Supply of Residential Buildings. PhD thesis, Saarland University, Saarbrücken, Germany. http://dx.doi.org/10.22028/D291-40488

Kuethe, S., Wilhelms, C., Zass, K., Heinzen, R., Vajen, K., Jordan, U., 2008. Modelling complex systems with TRNSYS SIMULATION STUDIO. In: Proceedings of the 7th ISES EuroSun Conference (EuroSun 2008). Lisbon, Portugal.

[![DOI](https://zenodo.org/badge/393104369.svg)](https://zenodo.org/badge/latestdoi/393104369)
