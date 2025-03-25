# GCW_Habitat_Analysis
Independent project completed Fall 2024, which measured the amount of Golden-cheeked Warbler habitat developed between 2001 and 2021. Full Python script uploaded from Jupyter Lab as gcwHabitat.ipynb
________________________________________________________________

The Golden-cheeked Warbler (GCW) is endemic to the Ashe Juniper and Oak woodlands of Texas. Since 1991, the GCW has been listed as endangered by the U.S. Fish and Wildlife Service due to “habitat loss and fragmentation” (USFWS, 1991).

However, the General Land Office and the Texas Public Policy Foundation have filed lawsuits in an attempt to remove the GCW from the endangered species list (Reed & Metzger, 2023). This decision will remove protections of their woodland habitat, and may open the door for increased development of natural Texas landscapes.

In my project, I evaluated how GCW habitat has changed from 2001 to 2021 in an effort to determine if delisting the bird is justified. In order for the GCW to be justifiably delisted, several requirements laid out in a “Recovery Plan” by the USFWS must be met. The Recovery Plan emphasizes that there must be “at least one viable, self-sustaining population in each of 8 Recovery Regions” throughout the GCW’s breeding range (USFWS, 1991). According to a study done at Texas A&M, habitat is the strongest predictor of GCW occurrence,  so I evaluated change in Oak-Juniper woodland in each of the 8 Recovery Regions to determine if GCW population stability has increased or decreased, thus providing insight for the delisting decision (Morrison et al., 2010).

Here you can see a map of the 8 Recovery Regions. 
![Recovery Regions](https://github.com/avaerickson/GCW_Habitat_Analysis/blob/main/images/gcw_recovery_regions.png?raw=true)

And here is a map that includes the GCW habitat.
![GCW Habitat](https://github.com/avaerickson/GCW_Habitat_Analysis/blob/main/images/gcw_habitat.png?raw=true)

Because my objective was to look at all 8 Recovery Regions separately, I used Python and arcpy functions to make the process more efficient.

First, I reclassified the land classes, creating one 'developed' class, and one 'forest' class. 

Note: NLCD forest reclassification did not isolate only Oak-Juniper woodland due to the land classifications available. However, my forest classification followed the Oak-Juniper range closely and was able to give relevant insight into where development had occurred.

Next, I created transition matrices for each of the 8 regions. I was specifically looking at the numbers highlighted in purple, which represent the amount of land that was forest in 2001 but had transitioned into developed land by 2021 (measured in km^2).
![Transition Matrices](https://github.com/avaerickson/GCW_Habitat_Analysis/blob/main/images/gcw_TMatrix.png?raw=true)

Then, I used the results from the transition matrix to update the attribute table with the results for each region.
![Amount Developed](https://github.com/avaerickson/GCW_Habitat_Analysis/blob/main/images/gcw_amnt_dev.png?raw=true)
![Percent Developed](https://github.com/avaerickson/GCW_Habitat_Analysis/blob/main/images/gcw_pct_dev.png?raw=true)

Both maps resulted in the same graduated symbols, suggesting a consistent relationship between total forest area developed and the percentage forest developed. This pattern indicates that certain regions are particularly susceptible to forest development, likely due to preferred landscape characteristics and economic drivers influencing land development.  

Overall, GCW habitat was lost to development in all 8 Recovery Regions. Because habitat is predictive of GCW occurrence, this suggests that there are less GCWs now than in 2001. Specifically, a majority of development has occurred along the I-35 corridor, with the most forest-to-developed land in Region 6, near San Antonio, TX. These are areas where recovery efforts should focus. Further research on this topic should include field verification of Golden-cheeked Warbler occurrence, as well as fragmentation and patch size analyses, which provide greater insight into species wellbeing. 

Data:

Texas Counties Data
https://gis-txdot.opendata.arcgis.com/datasets/texas-county-boundaries/explore 

“Land cover classification”, raster files, 2001 and 2021, from MRLC website 
https://www.mrlc.gov/viewer/ 

Other Sources:

Morrison et al., 2010
https://nri.tamu.edu/media/1107/gcwa_statewide_report.pdf 

Reed & Metzger, 2023
https://environmentamerica.org/texas/articles/fish-and-wildlife-service-will-soon-decide-fate-of-golden-cheeked-warbler/  

USFWS Recovery Plan
https://www.edwardsaquifer.org/wp-content/uploads/2019/02/1991_FWS_Golden-CheekedWarblerRecoveryPlan.pdf 
