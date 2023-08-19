# Destination Unreachable

This repository contains the code, data, and figures for the Internet Intelligence Research Lab's Sigcomm '23 paper, _Destination Unreachable: Characterizing Internet Outages and Shutdowns_ by authors Zachary S. Bischof, Kennedy Pitcher, Esteban Carisimo, Amanda Meng, Rafael Bezerra Nunes, Ramakrishna Padmanabhan, Molly Roberts, Alex C. Snoeren, and Alberto Dainotti.

## Repository structure

### Data (`./data/`)

The `./data/` directory contains the data files required for analysis. Currently, only the dataset created by the paper's authors is available in this repository. All other datasets mentioned below were created and managed by other groups. If you require specific versions of the data for replication, please contact us directly.

Description of files/directories:
- `./data/ioda/ioda_investigated_outages_cleaned_phase1+2.csv`: contains our manually curated list of IODA outages and shutdowns used throughout the paper. (Included in this repository)
- `./data/kio`: contains CSV files for each publication of AccessNow's #KeepItOn dataset (available [here](https://www.accessnow.org/campaign/keepiton/)). This data is used throughout the full paper.
- `./data/polisci`: contains the political and economic indicators that were used throughout the analysis in Sec 5.1 and 5.2 of the paper. Democractic indicies are made available by [V-dem](https://v-dem.net/data/the-v-dem-dataset/), macroeconomic data (e.g., GDP per capita, prevalence of broadband Internet access) was obtained from [The World Bank](https://databank.worldbank.org/), information on coups was collected as part of the [Global Instances of Coups](https://arresteddictatorship.com/coups/) dataset, data on elections made available by the [International Foundation for Electoral Systems-Election Guide](https://www.electionguide.org/), and data identifying protest events was obtained from the [Mass Mobilization in Autocracies Database](https://mmadatabase.org/).
- `./data/access-networks`: contains datasets related to autonomous system (AS) characteristics. This includes: CAIDA's prefix to AS mappings (availble [here](https://catalog.caida.org/dataset/routeviews_ipv4_prefix2as)), MaxMind's geolocation data (available [here](https://www.maxmind.com/en/solutions/ip-geolocation-databases-api-services)), and APNIC's eyeball dataset (available [here](https://stats.labs.apnic.net/aspop/)). These datasets are used in Sec 5.1 of the paper.
- `./data/soe`: contains data on state ownership of ASes as part of Carisimo et. al's IMC '21 paper (available [here](https://github.com/estcarisimo/state-owned-ases)). This dataset is used in part of Sec 5.1 of the paper.


###  Notebooks (`./notebooks`)

The `./notebooks` directory contains the Jupyter notebooks files used for preparing, cleaning, and merging the KIO and IODA datasets as well as notebook files for the paper's analysis. 

Description of files:
- `merge-kio-ioda.ipynb`: Contains the code to load and merge the IODA and KIO datasets. Also contains code to standardize/unify the different conventions used across different versions of the KIO dataset. This will create the merged dataset required for each of the analysis notebooks.
- `polisci-analysis.ipynb`: Contains code to generate most of the figures in Sec. 5.1 and 5.2 of the paper. This includes analysis of the distribution of Internet shutdowns and spontaneous outages across multiple poltical and socioeconomic indicators. 
- `state-ownership-analysis.ipynb`: Contains code to generate figures specificially in Sec 5.1.1. This includes the analysis on the relationship between Internet shutdowns and state ownership of the address space/eye-ball networks.
- `summary-and-technical-analysis.ipynb`: Contains code for generating figures related to a high-level summary of the KIO dataset (Sec 3.2), examples of multiple IODA outages being mapped to a KIO shutdown (Sec 4), and the temporal and technical indicators of Internet shutdowns (Sec 5.3).

