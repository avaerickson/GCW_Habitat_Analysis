# GCW_Habitat_Analysis
Independent Project completed Fall 2024, measuring amount of Golden-cheeked Warbler habitat that was developed between 2001 and 2021.
________________________________________________________________

The Golden-cheeked Warbler is a bird endemic to the Ashe Juniper and Oak woodlands of Texas. Since 1990, the Warbler has been on the U.S. Fish and Wildlife Service’s endangered species list due to “habitat loss and fragmentation”.

However, the General Land Office and the Texas Public Policy Foundation have filed lawsuits in an attempt to remove the Warbler from the endangered species list.This decision will remove protections of the Oak-Juniper woodlands, and may open the door for increased development of natural Texas landscapes.

In my project, I evaluated how Warbler habitat has changed from 2001 to 2021 in an effort to determine if delisting the bird is justified. In order for the Warbler to be justifiably delisted, several requirements laid out in a “recovery plan” by the USFWS must be met. This recovery plan emphasizes that there must be “at least one viable, self-sustaining population in each of 8 Recovery Regions” throughout the Warbler’s breeding range (USFWS, 1991).

According to a study done at Texas A&M, habitat is the strongest predictor of Warbler occurrence,  so I evaluated the change in oak-juniper woodland in each of the 8 Recovery Regions to determine if Warbler population stability has increased or decreased, thus providing insight for the delisting decision (Morrison et al., 2010).

Here you can see a map of the 8 Recovery Regions. 
________________________________________________________________

And here is a map that includes the warbler habitat.
________________________________________________________________

My objective was to characterize the transformation of Warbler habitat into developed land from 2001 to 2021 in each of the 8 Recovery Regions to gain an understanding of the stability of the species. Because I wanted to look at all 8 recovery regions separately, I used Python and arcpy functions to make the process more efficient.

First, I reclassified the land classes so that it was easier to look specifically at forest to developed land. I grouped all developed together to create one “developed” class and I grouped all forest together to create one woodland class. 

Grouping together all NLCD forest classes did not specifically isolate Oak-Juniper woodland, however this classification followed the Oak-Juniper range closely and was enough to give good insight into where development was happening.

Next, I created transition matrices for each of the 8 regions. I was specifically looking at the numbers highlighted in purple which represent the amount of land that was forest in 2001 that turned into developed land by 2021 (measured in km^2).
![Transition Matrices](https://github.com/avaerickson/GCW_Habitat_Analysis/blob/main/images/gcw_TMatrix.png?raw=true)

Then, I used the results from the transition matrix to update the attribute table of a shapefile for the entire breeding range, which allowed me to display the results.
![Amount Developed](https://github.com/avaerickson/GCW_Habitat_Analysis/blob/main/images/gcw_amnt_dev.png?raw=true)

Both maps resulted in the same graduated symbols, so the regions in which a lot of forest area is being developed, also have a high proportion of their forest being developed.

In conclusion, there has been Warbler habitat lost to development in every single Recovery Region. Because habitat is predictive of Warbler occurrence, this suggests that there may be less Warblers now than there were in 2001.Specifically, a lot of development is happening along the I-35 corridor,
With the most forest-to-developed land occurring in Region 6, around San Antonio. These are areas where we can try and focus recovery efforts the most. Further research on this project should include field verification of Golden-cheeked Warbler occurance, as well as fragementation and patch size analyses, which provide insight into species wellbeing. 

