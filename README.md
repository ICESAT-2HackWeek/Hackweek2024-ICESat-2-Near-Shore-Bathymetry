
# <p align="justify">Space Based LIDAR: Observing Near-Shore Bathymetry With NASA's Ice Cloud and land Elevation Satellite-2 (ICESat-2)</p>

## About ICESat-2
<p align="justify">
The ICESat-2 satellite uses an onboard laser system to send green laser light photons to Earth’s surface. The satellite emits visible laser pulses at 532 nm wavelength, which is a bright green color on the electromagnetic spectrum. This specific shade of bright green is what the filters on the satellite detector lets pass through in order to count the photons. Any other wavelength gets filtered out as background noise. The satellite is 310 miles (498 km) above the Earth’s surface. The ICESat-2 satellite precisely records the time-of-flight of individual photons as they travel from the instrument, reflect off Earth’s surface, and then are detected as they return to the instrument’s detector. These measurements allow scientists to calculate Earth’s surface elevation. By doing this, they are able to measure the height of everything on our planet, including sea ice, ice sheets, landforms, forest and tree canopies, ocean surface and clouds. 
</p>

<p align="justify">
Photons are tiny little particles of light, far too small to see individually. All light is made of photons. Only a small percentage of laser light photons make it back to the satellite, which are extremely valuable to scientific research. Here is DIY ("ICESat-2 Bouncy Ball Photon Collection Activity") to develop a gut feeling about the photon scattering process: 
</p><br />
https://icesat-2.gsfc.nasa.gov/sites/default/files/funzone/ICESat-2_PhotonCountingActivity_BouncyBalls_FINAL%20508%20Compliant.pdf

## Objective
<!-- Justify text in github's readme: https://stackoverflow.com/questions/66777538/justify-text-in-githubs-readme -->
<!-- Markdown Cheatsheet: https://github.com/tchapi/markdown-cheatsheet/blob/master/README.md -->
<!-- How to add images to README.md on GitHub?: https://stackoverflow.com/questions/14494747/how-to-add-images-to-readme-md-on-github -->
<!-- https://docs.github.com/de/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax -->
<!-- https://convertcase.net/ -->
_Parrish et al., 2019:_
<p align="justify">
"NASA’s Ice, Cloud, and Land Elevation Satellite-2 (ICESat-2) was launched in September, 2018. The satellite carries a single instrument, ATLAS (Advanced Topographic Laser Altimeter System), a green wavelength, photon-counting lidar, enabling global measurement and monitoring of elevation with a primary focus on the cryosphere. Although bathymetric mapping was not one of the design goals for ATLAS, pre-launch work by our research team showed the potential to map bathymetry with ICESat-2, using data from MABEL (Multiple Altimeter Beam Experimental Lidar)..."
</p><br />
<p align="justify">
i) We would like to combine time-series of ICESat-2 observations to create a near continuous (depending on the number and quality of the available ICESat-2 passes) near-shore bathymetry map. Furthermore, we would like to understand the impact of the Baltic sea storm surge on the seafloor erosion & deposition. The storm occured on October 20, 2023 and caused massive infrastructural damage along the north eastern coast of Germany.   
</p>

Here is more on the 2023 storm: 

https://www.uni-kiel.de/en/details/news/299-floods-adaptations-balticsea

https://www.surf-magazin.de/en/spots-and-areas/baltic-sea/flood-of-the-century-the-baltic-sea-storm-surge-2023-this-is-the-current-situation-at-the-spots/

<p align="justify">
ii) We would like to try our hands on developing machine learning models for bathymetric estimation. Can we establish models using optical spectral data (Sentinel-2, Landsat, Planet etc.) and ground reference bathymetric measurements?<br /> 
iii) We will also have a chance to peep into the depths of a drifting Arctic meltpond: Mystery Lake.
</p>

## Collaborators

Here is a biosketch of the team that we would like to put together for this project. You are welcome to join even if you don't fit into one of these categories. Willingness to Learn & Acceptance Towards Failures are the most important prerequisites.
* The ICESat-2 enthusiast
* The Machine Learning nerd
* The Ocean lover
* The Python/Google Colab/R/Google Earth Engine (GEE) guru(s)
* The Street Smart & Quick-Witted


## Data, Workflow, and Literature

### Data
<!-- New lines inside paragraph in README.md: https://stackoverflow.com/questions/24575680/new-lines-inside-paragraph-in-readme-md -->
<!-- Hidden markdown text on GitHub: https://stackoverflow.com/questions/46734820/hidden-markdown-text-on-github  -->
<!-- How to add empty spaces into MD markdown readme on GitHub?: https://stackoverflow.com/questions/44810511/how-to-add-empty-spaces-into-md-markdown-readme-on-github -->
<!-- How to create a new folder on a repository?: https://github.com/orgs/community/discussions/69927 -->
About ICESat-2: https://icesat-2.gsfc.nasa.gov/<br />  

ICESat-2 Algorithm Theoretical Basis Document for Global Geolocated Photon Data (ATL03):<br /> 
<p align="justify">
Precise latitude, longitude and elevation for every received photon, arranged by beam in the along-track direction. Photons classified by signal vs. background, as well as by surface type (land ice, sea ice, land, ocean), including all geophysical corrections. Segmented into several minute granules.
</p>
https://icesat-2.gsfc.nasa.gov/sites/default/files/page_files/ICESat2_ATL03_ATBD_r006.pdf<br />

ICESat-2 Photon Classification Using NASA Goddard Space Flight Center (GSFC) "Yet Another Photon Classifier" (YAPC) Algorithm: https://github.com/tsutterley/yapc<br />
<br />

YAPC Overview
<p align="justify">
https://yapc.readthedocs.io/en/latest/getting_started/Overview.html<br />
YAPC is a prototype photon classifer for the NASA ICESat-2 ATL03 Global Geolocated Photon product. It was developed by Jeff Lee (GSFC) with the goal of supporting and simplifying science applications for the ICESat-2. It is a customized inverse-distance kNN algorithm developed to determine the significance (or weight) of individual photon events. The weight of each photon is indicative of localized density based on it surrounding K neighbors and the inverse distances.
</p><br />

What Is SlideRule?<br />https://slideruleearth.io/<br />https://github.com/SlideRuleEarth<br />
<p align="justify">
SlideRule is a public web service with REST APIs for processing science data and returning results. It provides researchers and other data systems with low-latency access to generated data products using processing parameters supplied at the time of the request. SlideRule runs in AWS us-west-2 and has access to ICESat-2, GEDI, Landsat, and a growing list of other datasets stored in S3. While its web services can be accessed by any http client (e.g. curl), Python and Node.js clients are provided to make it easier to interact with SlideRule. 
</p>
<br />
The European harmonised bathymetry grid EMODnet Bathymetry: 
https://www.dhyg.de/images/fachbeitraege/DOI_10.23784_HN117_03.pdf<br />

A purely spaceborne open source approach for regional bathymetry mapping: Bahamas Median DEM<br />
https://ieee-dataport.org/documents/purely-spaceborne-open-source-approach-regional-bathymetry-mapping-bahamas-median-dem

### Workflow
* We will be using Google Colab for executing the Python notebooks. We would like to integrate the GitHub repository with Google Colab. Another great cloud computing platform is the NASA-funded CryoCloud, which is a JupyterHub built for NASA Cryosphere communities in partnership with the International Interactive Computing Collaboration. You can read more about these cool tools below.<br />  
  https://stackoverflow.com/questions/67553747/how-do-i-link-a-github-repository-to-a-google-colab-notebook<br />
  https://book.cryointhecloud.com/intro.html<br />
  https://2i2c.org/<br />
* Results and other documentations can be stored on Google Doc/Drive. I'll host some data on the University of Kiel cloud.
* For drafting a manuscript resulting from this work, I propose to collaboratively work on Overleaf. It is a collaborative cloud-based LaTeX editor used for writing, editing and publishing scientific documents: https://www.overleaf.com/

#### Project Essentials & Starters
* GitHub account: https://icesat-2hackweek.github.io/learning-resources/preliminary/github/
* ICESat-2 Bathymetry Overview: https://github.com/ICESat2-Bathymetry/Information
* Python tools to work with ICESat-2 and more: https://github.com/nholschuh/NDH_PythonTools
* Searching for the closest ICESat-2 flyover for a given AOI: https://github.com/ICESAT-2HackWeek/EverythingAnyWhereAllAtOnce
* Extracting sections of ICESat-2 tracklines, identifying bathymetry, and coastal morphology: https://github.com/ICESAT-2HackWeek/coastal_topobathy
* Processing ICESat-2 ATL03 photon returns into refraction corrected bathymetry and collocate the data to reflectance values from Landsat 8 multispectral data (Processed in SeaDAS: https://seadas.gsfc.nasa.gov/) to interpolate depth in optically shallow water: https://github.com/ArcticCartographer/ICESat-2-Satellite-Derived-Bathymetry-using-Landsat-8-data
* Satellite Derived Bathymetry (SDB) GUI: https://github.com/rifqiharrys/sdb_gui
* Satellite Derived Bathymetry in the coast of Thailand with ICESat-2: https://github.com/lookmeebbear/sdb_thailand
* Interactive Jupyter Book for wrangling, visualizing, and analyzing ICESat-2 observations: https://github.com/akpetty/icesat2-book
* Python tools for obtaining and working with elevation data from NASA's ICESat-2 mission and various data products (ATL00-ATL21): https://github.com/tsutterley/read-ICESat-2   

### Literature
The ICESat-2 Laser Altimetry Mission: https://ieeexplore.ieee.org/abstract/document/5461025 
$~$<br />

ICESat-2 Bathymetry Overview: https://github.com/ICESat2-Bathymetry/Information
$~$<br />

The Ice, Cloud, and land Elevation Satellite-2 (ICESat-2): Science requirements, concept, and implementation: https://icesat-2.gsfc.nasa.gov/sites/default/files/multimedia/Markus_etal_RSE_2017.pdf
$~$<br />

SlideRule: Enabling rapid, scalable, open science for the NASA ICESat-2 mission and beyond: https://joss.theoj.org/papers/10.21105/joss.04982
$~$<br />

icepyx-querying, obtaining, analyzing, and manipulating ICESat-2 datasets: https://joss.theoj.org/papers/10.21105/joss.04912
$~$<br />

A Framework for Automated Supraglacial Lake Detection and Depth Retrieval in ICESat-2 Photon Data Across the Greenland and Antarctic Ice Sheets: https://egusphere.copernicus.org/preprints/2024/egusphere-2024-1156/egusphere-2024-1156.pdf 
$~$<br />

For refraction correction of bottom return photons: Validation of ICESat-2 ATLAS Bathymetry and Analysis of ATLAS’s Bathymetric Mapping Performance: https://www.mdpi.com/2072-4292/11/14/1634<br />

The Multiple Altimeter Beam Experimental Lidar (MABEL), an airborne simulator for the ICESat-2 mission: https://ntrs.nasa.gov/api/citations/20120016023/downloads/20120016023.pdf<br /> 

The ICESat-2 mission: A global geolocated photon product derived from the Advanced Topographic Laser Altimeter System: https://www.sciencedirect.com/science/article/pii/S003442571930344X<br /> 

Evaluation of a Statistical Approach for Extracting Shallow Water Bathymetry Signals from ICESat-2 ATL03 Photon Data: https://www.mdpi.com/2072-4292/13/17/3548<br /> 

Developing an ICESat-2 Based Lake Bathymetry Product for Improved Reservoir Management: A Pilot Study over Lake Mead: https://icesat-2.gsfc.nasa.gov/sites/default/files/general_content_files/ICESat-2%20Applications%20Small%20Posters-FINAL.pdf<br /> 



## Getting Started
### Getting Started: Jupyter Notebooks
Please refer to the following tutorial from Hackweek 2023:<br />
https://github.com/ICESAT-2HackWeek/ICESat-2-Hackweek-2023/tree/main/book/tutorials/bathymetry<br />
https://github.com/ICESAT-2HackWeek/ICESat-2-Hackweek-2023/tree/main/book/tutorials/DataVisualization

### Important to Know
Github Forking (creating a copy of a repo on your own Github account) & Pull Request (requesting the owner of the original repo to accept the modifications that were made to the forked repo): https://www.earthdatascience.org/workshops/intro-version-control-git/about-forks/
<br /> 

How to Execute Jupyter Notebooks from GitHub: https://soshnikov.com/education/how-to-execute-notebooks-from-github/
<br />

Google Colaboratory is a research tool for machine learning education and research. It’s a Jupyter notebook environment that requires no setup to use: https://github.com/googlecolab/colabtools
<br />  

How to Share Google Colab Notebook on Github: https://www.youtube.com/watch?v=xNfiLvgG3iA
<br />

What is CryoCloud?: https://book.cryointhecloud.com/content/about.html<br />
<p align="justify">
"Substantial barriers exist for individual users to make the transition from their local systems to the cloud to accomplish research goals: cloud cost opacity, infrastructure deployment complexity, and a general lack of community awareness and knowledge, among others. We can overcome these barriers by building upon existing cloud-workflow models and creating infrastructure that allows researchers to seamlessly move their workflows wherever they can do their best work.

To optimize and expand this cloud-based model, CryoCloud is a NASA-funded project for a managed computing platform. The cloud environment is adapted to the current needs of researchers, provides cloud and community expert-led hackathon-style training workshops, and works towards development of new open-source tools for collaborative, open-science research. "
</p>
<br />






