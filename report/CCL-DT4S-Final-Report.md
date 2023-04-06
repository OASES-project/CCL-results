# Deliverables

- **D1. Workflow for creating a state-of-the-art hybrid LCA database: COMPLETED** <br>
The workflow is open source and available in a github repository: [https://github.com/OASES-project/CCL-results](https://github.com/OASES-project/CCL-results)
- **D2. Automatic tools for integrating and improving LCA data:  COMPLETED** <br>
The tool is available in the github repository [https://github.com/aleksandra-kim/gsa_framework](https://github.com/aleksandra-kim/gsa_framework)
- **D3. Set of LCA results for Swiss consumption: COMPLETED** <br>
The data are provided in a datapackage format. See report below
- **D4. Web tool for Swiss consumers: Unknown**


# Data validation

## Mining production volumes of selected metals

Process life cycle assessment, and as such process databases such as ecoinvent, is used ever more to perform footprint studies, i.e. modelling the total environmental footprint of a product, service or even household consumption, these databases need to cover global supply chains. Completeness therefore becomes ever more important for these databases. With this in mind we performed a validation check on the production volumes covered by the ecoinvent database version 3.9 for major metals (copper, aluminium, iron) in the supply chains of household consumption. 


[\\]: # (Copper demand is expected is expected to rise significantly over the next few decades due to the increasing use of copper intensive low carbon energy technologies. However, copper production, including mining, smelting, and refining, is very energy and green house gas intensive.)

The table below provides the an overview of the production volumes for copper, aluminium, and iron, in ecoinvent 3.9 and the real world values as taken from the sources provided. 
<p align = "center">
**Table 1: Comparison of production volumes of copper, aluminium, and iron in the ecoinvent database version 3.9 and real world data.**

| Metal | Production volume <br> ecoinvent <br> (kt)| Production volume <br> real world <br> (kt) | Reference year| Source |
|--------------|:-----:|:---:|:--:|---|
| Copper | 16.3 | 24.8 | 2021 |[Statista](https://www.statista.com/statistics/254917/total-global-copper-production-since-2006/), last accessed April 6 2023 |
| Aluminium | 69.0  | 136,000 | 2020 | [U.S. Geological Survey Jan 2021](https://pubs.usgs.gov/periodicals/mcs2021/mcs2021-bauxite-alumina.pdf), last accessed April 6 2023 |
| Iron | 665,633 | 1,630,000 | 2021 | [U.S. Geological Survey Jan 2022](https://pubs.usgs.gov/periodicals/mcs2022/mcs2022-iron-ore.pdf), last accessed April 6 2023 |

## Mass balance within ecoinvent
As part of the validation effort we got in touch with Han de Wachter from Ciraig in Montreal, who has developed an algorithm to check and balance the mass flows of all ecoinvent processes, both on the product level as well as the elementary flow level. Although preliminary results were shared, the work is still in early stages but will be published in the future. 


# The consumption model calculation
The household consumption model was updated as described in the CCL preliminary report from Januray 2023. The latest addition to the model was to update the ecoinvent database to the latest versio 3.9.1, which posed a tehcnical challenge due to internal changes in the ecoinvent database. Furthermore, the model now includes the possibility to include the sampling variance of the households inlcuded in the survey as a source of variance for the impact results. Two options are provided, one where the sampling variance is modelled as a lognormal distribution with a mean and standard deviation derived from the household expenditure data. The second option allows for direct sampling from the houshold expenditure survey, as such forgoing any assumptions on the shape of the distribution. 

The data package provided is based on the XXX option.

 

# Results of the household consumption model

Here we present a few key results from the analysis of the Swiss household consumption footprint. We note that the full results are provided in the datapackages that can be used for (online) calculation tool. The results presented here highlight a few possibilities of 
the updated consumption model and the  available data. 

The full set of results is provided as a datapackage of which the structure is described in section XXX.

The results of the household consumption impacts are provided for the average Swiss household as well as differentiated across the following demographic categories and combinations thereof. 

<p align = "center">
**Table 2: Demographic categories used for differentiation of the household consumption footprints**

| Grossregion |	Einkommensklasse |	Haushaltstyp |
|---|---|---|
1.	Genferseeregion | 1. Fünftel (<4914) | 1. Einpersonenhaushalte unter 65 | 
2.	Espace Mittelland |2. Fünftel (4914–7264) | 2. Einpersonenhaushalte ab 65 |
3.	Nordwestschweiz | 3. Fünftel (7265–9990) | 3. Paarhaushalte (beide unter 65) ohne weitere Haushaltsmitglieder |
4.	Zürich | 4. Fünftel (9991–13621) | 4. Paarhaushalte (mindestens eine Person ab 65) ohne weitere Haushaltsmitglieder | 
5.	Ostschweiz | 5. Fünftel (≥13622)	 | 5. Einelternhaushalte mit Kindern (mindestens eines unter 25) ohne weitere Haushaltsmitglieder |
6.	Zentralschweiz | | 6. Paarhaushalte mit Kindern (mindestens eines unter 25) ohne weitere Haushaltsmitglieder | 
7.	Tessin	 | |

As to comply with the privacy rules of the Federdal Statistics Office, the household clusters have a minimum size of 150 households. Combinations of the above demographic categories that had a sample size smaller than 150 households were aggregated, meaning that not all combinations are provided in the results datapackage.



## Contribution analysis GWP100 and UBP

Figure 1 shows the annual per person climate impact, as the global warming potential, of household consumption for the average Swiss household, as well as the 6 household types distinguished by the Federal Statistics Office (table 2), differentiated according to consumption category The narrow yellow bars provide the per person annual gross income for the household. The number in brackets at the end of each household type name gives the average number of people (including children) for each household. These results were calculated using deterministic approach, i.e., uncertainties were not considered here, neither the sampling variance of households, not the uncertainties in the background database.

<p align = "center">
![gwp_contributions](./figures/GWP100_byHousholdType_bySector_inclMeanIncomePP.pdf)
<p align = "center">**Figure 1**

Figure 2 shows the total environmental impact of household consumption as the ecological scarcity indicator, which includes various impacts such as global warming potential, land use, and ecotoxicity in a single score (ecopoints, or Umweltbelastungspunkte UBP). The breakdown of the the total impact for the average household by impact compartment is presented in figure 3, which shows tha land use and cliamte change dominate the environmental impacts of Swiss household consumption. 

<p align = "center">
![ubp_contributions](./figures/EnvironmentalImpact_byHousholdType_bySector_inclMeanIncomePP.pdf)
<p align = "center">**Figure 2**

<p align = "center">
![ubp_compartment_contributions](./figures/total_env_imp_by_compartment.pdf)
<p align = "center">**Figure 3**

## Uncertainty analysis of gwp100 household types

The updates to the household consumption model by the CCL project also included the option to do a full stochastic analaysis, in other words to take the sampling variance of household consumption into account, and provide impact distributions rather than static values. Figure 4 provides such distributions for the global warming potential impact of the 6 household categories as well as the average Swiss household. The yellow line and orange dashed line provide the mean and median of the distributions respectively. The histograms in figure 4 show the 1-99 percentile range of all samples.

<p align = "center">
![gwp_distributions](./figures/gwp100_distributions_householdtypes.pdf)
<p align = "center">**Figure 4**

Such an analysis shows that the variance between households is vary high indeed. We note that these distributions also include the database uncertainty but that the variance of the distributions is dominated by the household sampling variance, i.e. the differences in consumption patterns between the households. 