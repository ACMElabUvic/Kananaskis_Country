# Willmore
This repository contains data, R scripts and associated outputs, and other materials necessary for the Applied Conservation and Macro Ecology (ACME) laboratory's research program in Kananaskis Country. Data was collected from 2011-2012, and continued as summer only data for 2013 and 2014. 
<hr>

The Kananskis Country project has changed hands several times with respect to field deployment and data management. As a result there have been revised versions of the dataset, with ultimately 159 sites selected as useable for future analysts. Unfortunately some of the documentation of the original data extraction is missing, but can be read in the original manuscripts produced from this dataset (see relevant literature). Below is a README file from an analyst from 2020 who described the revision to 159 sites:

*Kananaskis Data: README*
*2023-05-02*

*Data from Kananaskis Country were collected under the East Slopes Predators Project, an Alberta Research Council and Alberta Environment & Parks (AEP) collaboration. Nicole Heim (MSC student, University of Victoria) was field data collection lead.*

*Data were collected by Nicole and AEP staff summer and winter 2011-2012; given the success of the project it continued as a summer-only data 2013- and 2014. During this second period AEP staff were responsible for data collection and organization.*

*Due to a lack of central organizing structure the data were messy. Sites were moved slightly between years or duplicated with new names, others lack naming conventions altogether.*

*In 2020 this mass of data was re-examined, cleaned, renamed. 159 spatially independent sites were identified and this subset is the most reliable and should be used.*
<hr>

### GENERAL INFORMATION

**Project Information**   
Details for the Kananaskis Country research program [here](http://www.acmelab.ca/kananaskis.html).

Also visit the [ACME website](http://www.acmelab.ca) more information about the ACME lab.

**Author Information (data):**  
 Principal Investigator Contact Information  
 Name: Jason T. Fisher, PhD   
 Institution: University of Victoria  
 Address: 3800 Finnerty Rd, Victoria, BC V8P 5C2  
 Email: [fisherj@uvic.ca](mailto:fisherj@uvic.ca) 

**Author Information (code):**  
 Data Analysis Contact Information  
 Name: Andrew Barnas, PhD   
 Institution: University of Victoria  
 Address: 3800 Finnerty Rd, Victoria, BC V8P 5C2  
 Email: [andrew.f.barnas@gmail.com](mailto:andrew.f.barnas@gmail.com) 

 ### DATA & FILE OVERVIEW
**inputs**

This folder contains both summarized and raw data data products (e.g. raw camera trap data csv files) used to produce key products in the outputs folder. 
*Files in main folder*
1) WillmoreSummer_alldata.csv : this is a binded file of the individual timelapse files from each camera site during the SUMMER study. The individual camera site csv files were unavailable
2) WillmoreWinter_alldata.csv : this is a binded file of the individual timelapse files from each camera site during the WINTER study. The individual camera site csv files were unavailable
3) SUMMER WILLMORE BIODIVERSITY SITE LOCATIONS CORRECTED 2017 : this file contains the location of each camera site (UTMs)
4) WillmoreLandCoverAll.csv : this file contains natural landcover data for the proportion area of a circular buffer around each camera site. Grid codes keys from the original data extraction are provided in other/Wilmore_Griz_Land_Class_Key.jpeg
5) WillmoreNDVI2008.csv : this file contains mean NDVI for each camera site in 2008
6) WillmoreNDVI2012.csv : this file contains mean NDVI for each camera site in 2012
7) WillmoreTRI.csv : this file contains mean TRI for each camera site
8) WW_HumanFootprintCover_corrected.csv : human footpring cover for each camera site (details below)

**outputs**

This folder contains the four key data products needed to move forward with additional analyses; 1) the raw detections recorded from cameras (including blank images, nothing has been filtered), 2) a summary of independent detections of wildlife species at each camera site to the standard 30 minute threshold, 3) the GPS locations of individual camera sites, and 4) covariates associated with each camera site extracted across multiple radius buffers (details below)

**relevant literature**  
This folder provides pdf copies of previously published papers using the Willmore Wilderness remote camera dataset. The purpose of this folder is to provide background/information on previously published work using this dataset. Note that sample numbers may vary between individual manuscripts due to specifics of individual projects, as well as the multiple deployment designs within the Willmore dataset.
 * Barnas et al. 2024 How landscape traits affect boreal mammal responses to anthropogenic disturbance.
 * Fisher and Bradbury 2014 A multi-method hierarchical modeling approach to quantifying bias in occupancy from noninvasive genetic tagging studies
 * Fisher et al. 2011 Body mass explains characteristic scales of habitat selection in terrestrial mammals
 * Fisher et al. 2013 Spatial segregation of sympatric marten and fishers- the influence of landscapes and species-scapes
 * Fisher et al. 2014 Spatial patterns of breeding success of grizzly bears derived from hierarchical multistate models
 * Frey et al. 2020 Move to nocturnality not a universal trend in carnivore species on disturbed landscapes
 * Khan et al. 2023 Shifts in diel activity of rocky mountain mammal communities in response to anthropogenic disturbance and sympatric invasive white-tailed deer
 * Stewart et al. 2015 Wolverine behavior varies spatially with anthropogenic footprint - implications for conservation an inferences about declines

**other**  
This folder contains information from the original data production necessary for producing key data products. 
1) Wilmore_Griz_Land_Class_Key.jpeg : translation keys for landcover classes
2) HFI2010_Metadata.pdf - detailed description of human feature index used in the data extraction process (see below)

<hr>

### **DETAILS ON OUTPUTS** 
### Data specific information for : [outputs/willmore_camop.csv]  

* **Number of variables/columns:** 5
* **Number of observations/rows:** 115 (one per camera site) 

**Variable List:**
* **site** : camera site ID
* **Easting** : camera site Easting location
* **Northing** : camera site Northing location
* **start_date** : first day of camera operation as recorded by a camera trigger (no timelapse function used)
* **end_date** : last day of camera operation as recorded by a camera trigger (no timelapse function used)

### Data specific information for : [outputs/willmore_detections_raw.csv]  

* **Number of variables/columns:** 3
* **Number of observations/rows:** 151140

**Variable List:**
* **site** : camera site ID
* **datetime** : the datetime (year-month-day hour:minute:second) of the first camera image of each independent detection. Multiple images may be taken during a detection event, and this data has been sliced to the first image for simplicity. Note there was an error in the raw data resulting in no "seconds" being recorded from the timelapse data, therefore all detections end at the top of the hour (e.g. 6:03:00 AM). This should be of little consequence, but is annoying. 
* **species** : the species in the independent detection. Note this still contains "Unknowns" and some blanks, so this will need to be filtered/cleaned before any analysis.

### Data specific information for : [outputs/willmore_30min_independent_detections.csv]  

* **Number of variables/columns:** 5
* **Number of observations/rows:** 19072 (one row for each independent detection of a species at each site) 

**Variable List:**
* **site** : camera site ID
* **datetime** : the datetime (year-month-day hour:minute:second) of the first camera image of each independent detection. Multiple images may be taken during a detection event, and this data has been sliced to the first image for simplicity. Note there was an error in the raw data resulting in no "seconds" being recorded from the timelapse data, therefore all detections end at the top of the hour (e.g. 6:03:00 AM). This should be of little consequence, but is annoying. 
* **species** : the species in the independent detection. Note this still contains "Unknowns" and will need to be filtered/cleaned before any analysis.
* **timediff** : the difference in time between subsequent independent detections (mins). Note this could be calculated using the datetime column between subsequent detections. NA's represent the first detection of a species at a given camera, as there can be no difference in time from this event to a previous event. 
* **Event.ID** : a unique identifier for a species' independent detection at a camera site. 

### Data specific information for : [outputs/willmore_covariates.csv]  

* **Number of variables/columns:** 38
* **Number of observations/rows:** 2300 (115 camera sites, 20 repeat observations/one observation per radius measure)

**Variable List:**
* **site** : camera site ID
*  **radius** : the circular buffer (m) around which proportional cover for other covariates is measured
*  **bpsdl** : borrowpits, sump, dugouts and lagoons: Artificial holding or treatment ponds for industrial, agricultural or municipal wastewater. Human made water and sewage lagoons used for municipal purposes.
*  **cultivation** : Agricultural areas used for cultivation
*  **disturbedvegetation** : Disturbed vegetation that does not fit any other category of human footprint.
*  **harvestareas** : Areas where forestry operations have occurred (clearcut, selective harvest, salvage logging, etc.)
*  **industrial_sites** : a summary feature of many industrial sites (see pages 75-76 of other/HFI2010_Metadata.pdf)
*  **landfill** : Large area of raised land, indicating buried garbage. Some landfills have evidence of surface revegetation and garbage dispersed throughout designated extent. They may also have large perimeter berns or fences
*  **mine_sites** : a summary feature of many mine sites (see pages 60-61 of other/HFI2010_Metadata.pdf)
*  **othervegsurfacesrecreation** : a summary feature of many other vegetated surfaces (see pages 97 of other/HFI2010_Metadata.pdf)
*   **pipelines** : A line of underground and over ground pipes, of substantial length and capacity, used for the conveyance of petrochemicals. (Technically a summary feature, but basically the same, see page 167 of other/HFI2010_Metadata.pdf)
*   **railways**: a summary feature of many railway types, see page 48 of other/HFI2010_Metadata.pdf)
*   **resevoirs** : a body of water created by excavation or the man made damming of a river or stream
*   **residential_areas** : Rural developments (10 - 100 buildings per quarter section).
*   **roads** : a summary feature of road types (see pages 38-39 of other/HFI2010_Metadata.pdf)
*   **seismiclines** : a summary feature of different seismic lines (see page 174 of other/HFI2010_Metadata.pdf)
*   **transmissionlines** : A utility corridor >10 m wide with poles, towers and lines for transmitting high voltage electricity (voltage greater than 69 kV). (Technically a summary class, see page 112 of other/HFI2010_Metadata.pdf)
*   **verge** : no clear description - RECOMMEND REMOVAL OR NOT USING
*   **wellsites** : no clear description, but given there are two feature classes for active and abandoned wellsites, this is likely a combination of the two.
*   **wind_gen_facilities** : Wind turbines, operational or former, visible on imagery. Digitized to represent original land disturbance from construction.
*   **dense_conifer** : dense conifer
*   **moderate_conifer** : moderate conifer cover
*   **open_conifer** : open conifer cover
*   **mixed** : likely mixed tree species cover
*   **broadleaf** : deciduous tree cover
*   **treed_wetland** : wetlands with a high amount of trees
*   **shrub** : shrubs
*   **herb** : not sure, herbs? maybe oregano? (being cheeky, I can't find anything on this)
*   **open_wetland** : open wetlands lacking trees
*   **barren** : open landscape devoid of vegetation
*   **water** : open water, different from wetland.
*   **shadow_or_no_data** : error in the extraction process from shadows
*   **snow_or_ice** : snow or ice cover
*   **regeneration** : regenerating vegetation
*   **cloud_or_no_data** error in the extraction process from clouds
*   **mean_ndvi_2008** : mean ndvi value within a 1000m buffer of the camera sites from 2008
*   **mean_ndvi_2012** : mean ndvi value within a 1000m buffer of the camera sites from 2012
*   **mean_tri** : mean terrain ruggedness index at each camera site

