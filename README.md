# FTOT-SCR 

Freight and Fuel Transportation Optimization Tool - Supply Chain Resilience 

## Description
FTOT is a flexible scenario-testing tool that optimizes the transportation of materials for future energy and freight scenarios.  FTOT models and tracks commodity-specific information and can take into account conversion  of raw materials to products (e.g., crude oil to jet fuel and diesel) and the fulfillment of downstream demand. FTOT was developed at the US Dept. of Transportation's Volpe National Transportation Systems Center.

## Installation 
To install, clone this repository to a directory `C:\FTOT-SCR`. Follow instructions from the main FTOT-Public repository to install supporting Python packages. 

## Running the Scenario

### Generating Input Files
FTOT-SCR relies on several scripts to create input files for the tool. The 

File | Inputs | Outputs
--- | --- | ---
`1_Seismic_Events.py` | faultdata.xlsx <br> point.txt | seismic_catalog.npy
`2_Scenario_Generation.py` | FaultData.xlsx <br> point.txt <br> seismic_catalog.npy |  earthquake_events.npy <br> scenario_GFT.npy <br> scenario_forest.npy <br> scenario_earthquake.npy
`3_Facility_Capacity.py` | rmp.csv <br> proc.csv <br> dest.csv <br> rmp_Xycoordinate.txt <br> proc_Xycoordinate.txt <br> dstXYcoordinate.txt <br> Earthquake files | facility_cap.npy <br> facility_cap_noEarthquake.npy <br> facility_DS.npy <br> CatalystReplace_cost.npy
`4_Bridge_Damage.py` | seismic_catalog.npy <br>  earthquake_events.npy <br> HighwayBridge_3state.txt <br>  MiddlePoint_Road.txt <br> bridge_location.npy <br> Earthquake files | BDI.npy <br> bridge_DS.npy
`5_Edge_Capacity.py` | HighwayBridge_3state.txt <br> Relationship_BridgeRoad_3_state.txt <br>  MiddlePoint_Road.txt <br> earthquake_events.npy  <br> BDI.npy <br> bridge_ds.npy | edge_cap.npy
`6_RepairTime_Cost.py` | Relationship_BridgeRoad_3state.txt <br> seismic_catalog.npy <br> earthquake_events.npy <br> BDI.npy <br> bridge_DS.npy <br> edge_cap.npy <br> facility_cap.npy <br> facility_DS.npy | repair_costs.npy <br> repair_time_edge.npy <br> repair_time_facility.npy <br> total_repair_time.npy

## Contributing 
* Add bugs and feature requests to the Issues tab for the Volpe Development Team to triage.

## Credits: 
* Dr. Ji Yun Lee (WSU)
* Jie Zhao (WSU)
* Dr. Kristin Lewis (Volpe) <Kristin.Lewis@dot.gov>
* Matthew Pearlson (Volpe) <Matthew.Pearlson@dot.gov> 
* Gary Baker (Volpe) 
* Olivia Gillham (Volpe) 
* Michelle Gilmore (Volpe) 
* Alexander Oberg (Volpe) 
* Dr. Scott B. Smith (Volpe) 
* Amy Vogel (Volpe)
* Amro El-Adle (Volpe)
* Kirby Ledvina (Volpe)
* Mark Mockett (Volpe)

## Project Sponsors:
The development of FTOT that contributed to this public version was funded by the U.S. Federal Aviation Administration (FAA) Office of Environment and Energy and the Department of Defense (DOD) Office of Naval Research through Interagency Agreements (IAA) FA4SCJ and FB48CS under the supervision of FAA’s Nathan Brown and by the U.S. Department of Energy (DOE) Office of Policy under IAA VXS3A2 under the supervision of Zachary Clement. Any opinions, findings, conclusions or recommendations expressed in this material are those of the authors and do not necessarily reflect the views of the FAA nor of DOE.

## Acknowledgements:
The FTOT team thanks our Beta testers and collaborators for valuable input during the FTOT Public Release beta testing, including Dane Camenzind, Kristin Brandt, and Mike Wolcott (Washington State University), Mik Dale (Clemson University), Emily Newes and Ling Tao (National Renewable Energy Laboratory), Seckin Ozkul, Robert Hooker, and George Philippides (Univ. of South Florida), and Chris Ringo (Oregon State University).

## License: 
This project is licensed under the terms of the FTOT End User License Agreement. Please read it carefully.
