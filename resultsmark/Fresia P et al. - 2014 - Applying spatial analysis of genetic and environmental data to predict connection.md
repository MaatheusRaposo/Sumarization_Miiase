# Applying spatial analysis of genetic and environmental data to predict connection corridors to the New World screwworm populations in South America
Pablo Fresia
Micha Silver
Thiago Mastrangelo
Ana Azeredo-Espin
Mariana Lyra

a Departamento de Entomologia e Acarologia , Escola Superior de Agricultura "Luiz de Queiroz" , Universidade de São Paulo , Av. Pádua Dias , No. 11 , CEP 13400-970 Piracicaba , SP , Brazil
Departamento de Entomologia e Acarologia
Escola Superior de Agricultura "Luiz de Queiroz"
Universidade de São Paulo

Av. Pádua Dias No. 11
13400-970
Piracicaba
CEP SP
Brazil, b Arava Development Co. Ltd. , Arava , Israel
Arava Development Co. Ltd

Arava
Israel, c Centro de Biologia Molecular e Engenharia Genética and Instituto de Biologia , Universidade Estadual de Campinas , Rua Cândido Rondon No. 400 , CEP 13083-875 Campinas , SP , Brazil
Centro de Biologia Molecular e Engenharia Genética and Instituto de Biologia
Universidade Estadual de Campinas

Rua Cândido Rondon No. 400
13083-875
Campinas
CEP SP
Brazil, d Departamento de Zoologia , Instituto de Biociências , Universidade Estadual Paulista , Av. 24 A, No. 1515 , Bela Vista , CEP 13506-970 Rio Claro , SP , Brazil
Departamento de Zoologia
Instituto de Biociências
Universidade Estadual Paulista

Av. 24 A, No. 1515
13506-970
Bela Vista Rio Claro
CEP SP
Brazil, P Departamento de Entomologia e Acarologia , Escola Superior de Agricultura "Luiz de Queiroz" , Universidade de São Paulo. Av. Pádua Dias, No. 11 , CEP 13400-970 , Av. Pádua Dias , No. 11 , CEP 13400-970 Piracicaba , SP , Brazil. . Fresia).
Departamento de Entomologia e Acarologia
Escola Superior de Agricultura "Luiz de Queiroz"

Universidade de São Paulo. Av. Pádua Dias, No. 11 Av. Pádua Dias No. 11
13400-970 13400-970
Piracicaba
CEP CEP SP
Brazil Fresia

Published on April 14, 2014

The myiasis causing New World screwworm (NWS) fly is responsible for substantial losses to livestock breeders in the Americas. Due to the negative impact of the NWS fly in animal health, expansion of successful NWS fly eradication programmes is under discussion. However, the effects of geography and environmental diversity on NWS population structure and migration patterns need to be assessed before any political decision is made to implement such a programme. We present a GIS tool to construct potential connection corridors among sampling localities based on genetic and environmental data. We integrate, through a home-made python script, a friction raster based on a Maxent niche model and the pairwise ˚ST statistic. Among 38 NWS fly sampling localities from South America, we find a high population connectivity among the sampling localities from the south of the Amazon region. The region along the Atlantic Ocean was identified as the most probable migration corridor between the north (NAG) and the south (SAG) of the Amazon region. The approach highlighted previously undetected population structure within NAG showing low to medium connectivity through the Andes, correlating with current understanding of NWS fly migration in South America. Also, the approach is flexible, allowing future research to incorporate other niche simulations and genetic differentiation metrics. With this flexibility, the tool could become part of any AW-IPM by helping to target regions for control.

### Introduction
The myiasis causing fly, Cochliomyia hominivorax (Coquerel, 1858) (Diptera: Calliphoridae), bearing common name the New World Screwworm (NWS) fly, remains an important pest, causing substantial losses to livestock breeders (e.g. Vargas-Teran et al., 2005). The species has been eradicated from North America and continental Central America using an area-wide integrated pest management approach (AW-IPM) based on the sterile insect technique (SIT) (Klassen and Curtis, 2005). Due to its negative impact on animal health throughout South America and some Caribbean islands, there is an obvious interest to expand the successful NWS fly eradication programmes to the current non-free areas. However, before the implementation of a NWS fly control programme in South America, and in addition to political decisions, some questions about the effect of geography and environmental diversity need to be answered in order to achieve an efficient management of populations. For example detecting geographic barriers or environmental discontinuities that limit gene flow, determining population size and the number of generations in target areas, are some of the important issues that should be addressed before launching any control programme.

Our earlier studies showed that current NWS fly populations are geographically structured in at least four main regional groups: Cuba, Dominican Republic and the North (NAG) and South Amazon (SAG) regions (Lyra et al., 2009;Fresia et al., 2011). Fresia et al. (2013), used an approximate Bayesian computation (ABC) analysis to investigate the phylogeography of the NWS fly; their work suggested that NAG originated from populations of North and Central America and SAG diverged from NAG in a process that involved at least two stages: the first occurred at the end of the Last Glacial Maximum (15,,000 years before present (YBP)) and the second in the transition between the Pleistocene and the Holocene eras (9100-11,000 YBP). The unique geographic barrier clearly detected in South America in this study seemed to be the Amazon region (Mastrangelo et al., 2014). But the identified areas north and south of the Amazon region are too large to be considered as targets for the species control. Furthermore, no investigation of possible migration routes of NWS fly (i.e. path and direction) was done.

The relatively recent development of statistically rigorous methods based on the coalescent theory (Kingman, 1982, reviewed in Hickerson et al., 2010;Knowles, 2009;Kuhner, 2008;Nielsen and Beaumont, 2009;Riddle et al., 2008) have enhanced phylogeographical inferences on species historical demography and population divergence based on genetic data. In parallel, geospatial data (e.g. landcover, climate, elevation, geology) and ecological niche modelling (ENMs) (Phillips et al., 2006) have been applied in phylogeographic studies. A recent review by Chan et al. (2011) identified many empirical examples that have benefited greatly by merging these data, but as the authors pointed out, relatively few phylogeographic studies have explicitly incorporated geospatial information. The example that identified dispersal corridors and estimated the degree of current and historical migration in populations of Oplurus cuviere, based on nuclear and mitochondrial DNA sequences, is of particular interest to the work developed here. Geographic Information Systems (GIS) are equipped with a variety of visualization and geostatistical tools in an integrated environment that could be useful to investigate phylogeographic patterns and processes (see Kidd and Ritchie, 2006;Kozak et al., 2008;Richards et al., 2007).

The understanding of animal movement and/or gene flow among habitat patches is a central question of phylogeographic studies. Its quantification and the degree to which landscape promotes or hinders the movements for a given species are essential to conservation management decisions (Calabrese and Fagan, 2004). Habitat connectivity studies are much used in conservation biology (Fischer and Lindenmayer, 2007), but rarely in pest management programmes.

Temperature, rainfall and moisture have been identified as determinants of the NWS fly life cycle (Lindquist and Barrett, 1945;Parman, 1945;Hightower et al., 1966;Hightower, 1969;Goodenough et al., 1983;Carballo et al., 1991;Stuart et al., 1995;Coronado and Kowalski, 2009), pupae and adults being the critical life stages influenced by the weather (Gutierrez and Ponti, 2014). The ecotone, between the forest and open savannah were identified as the preferred habitat of the NWS fly (Mangan and Thomas, 1989;Parker et al., 1993;Phillips et al., 2004;Garcia et al., 2007). Based on this knowledge, a previous Maxent niche model for the NWS fly (Fresia et al., 2013) and several trials performed we chose the variables that are most likely to explain the current spatial distribution of the NWS fly. The main objective of this work was to develop a GIS tool to construct and analyse potential migration corridors among sampling localities based on genetic and environmental data. Our purpose is to discuss the migration paths of the NWS fly populations in South America using the ˚ST statistic (Excoffier et al., 1992) specially developed for DNA sequences, which is analogous to the oldest and most widely used metrics of genetic differentiation (F ST ) (Wright, 1931), and the ecological niche modelling approach of Maxent (Phillips et al., 2006). We call these corridors "connection corridors" in an attempt to reflect the dual sources of the connection: both genetic distance and environmentally suitable paths of migration from the ecological niche modelling.

### Materials and methods
### NWS fly samples and genetic dataset
The genetic dataset analyzed in this study is a compilation of the data matrices for South American NWS flies from Fresia et al. (2011) and Mastrangelo et al. (2014). It includes sequences of three mitochondrial DNA fragments, corresponding to the B domain of the A + T-rich region ("control region"; CR) and partial sequences of the genes cytochrome c oxidase subunit I (COI) and subunit II (COII) from 408 NWS fly individuals sampled in 38 locations. Table 1 shows sample locations, sample sizes and haplotype distributions included in the analyses. For analytical purpose we only include localities with sample size higher than 4 (see Lyra et al., 2009). Sampling details, sequencing procedures and haplotype definition are described in Fresia et al. (2011) and Mastrangelo et al. (2014).

### Predicting population connection corridors
The approach to estimate possible connection corridors among the sampling localities consists of three stages: (1) an estimate of a genetic distance between the NWS fly individuals sampled at different locations, (2) the creation of a species habitat suitability model based on environmental data, and (3) statistical analysis using a GIS framework which combines the genetic distance matrix and habitat suitability model. This approach is a modification of methods described in the Supplementary material of Chan et al. (2011).

### Genetic distance
population differentiation was assessed using the pairwise ˚ST values calculated following the method of Hudson et al. (1992) using Arlequin software v3.5 (Excoffier and Lischer, 2010). Statistical significance was assessed by 10,000 permutations. The analysis was performed based on unambiguous haplotypes previously defined from a combined fragment of 1752 bp, that included the CR, COI and COII sequences considering pairwise distance between haplotypes.

For the interpretation of pairwise ˚ST values, we followed Hartl and Clark 1997 (and references there in) and considered that value lying in the range 0-0.05 indicates little genetic differentiation; values between 0.05 and 0.15, moderate differentiation, values between 0.15 and 0.25, large differentiation; and values above 0.25, very large genetic differentiation.

### Ecological niche modelling (ENM)
A map was generated showing the range of habitat suitability for the species based on it ecological tolerance. The habitat suitability grid was estimated for current climate conditions using the Maxent software v3.3.3k (Phillips et al., 2006) based on four environmental predictors (BIO5, BIO13, altitude, landcover) and a set of georeferenced NWS fly observations. The list of 134 locations of known NWS infestation over the past decades was compiled from the literature (Table S1) and formatted as a comma-separatedvalues (CSV) table to be used as the basis for the "presence only" algorithm used by Maxent. The climatic layers, BIO5 (maximum temperature of warmest month) and BIO13 (precipitation of wettest month), and the elevation dataset covering the continent of South America were obtained from WorldClim database (http://www.worldclim.org) at a resolution of 2.5 km. The range of temperatures in BIO5 data was from 7 to 35 degrees average maximum temperatures over a month. Rainfall in the wet months, BIO13, ranged across the continent from 20 to over 850 mm monthly average. The altitude data included elevations from sea level to peaks of over 6200 m in the Andes. Additionally, landcover data was obtained from the Global Landcover 2000 project (http://bioval.jrc.ec.europa.eu/products/glc2000/products.php    Global Land Cover, 2003) at the same resolution. This landcover data set is based on a land cover classification (LCC) containing 18 broad categories (see Appendix A, Table S2). No attempt was made to split the landcover classes, nor to evaluate the influence of each separate class on the final habitat suitability matrix: we considered the LCC as a whole. The landcover and environmental data sets were converted to the ArcInfo ASCII format, required by Maxent, using tools from the Geospatial Data Abstraction Library (GDAL, http://gdal.org) and maintained at their original resolution of 2.5 km.

### Statistical analysis using a GIS framework
Spatial analysis of the pair-wise genetic distance matrix together with the habitat suitability model was performed using GRASS-GIS (GR Development Team, 2012, http://grass.osgeo.org). A custom python script (https://github.com/micha-silver/popgen-gis/r.hsmtolcp.py) was developed to loop over all the 38 relevant locality pairs in the pairwise genetic distance matrix, to calculate the connection corridor between each pair of localities (based on the habitat suitability data), and then to merge all the corridors into a continental map of predicted connection corridors. Various GIS map algebra modules were used within the procedure.

The input parameters to the python script included:

• The habitat suitability model (hsm). This raster data was inverted to create a "friction" raster by doing the raster map calculation: friction = 1 -hsm.

• A csv formatted table of the ˚ST pair-wise matrix. • A csv formatted table of the p-values for the ˚ST pair-wise values. • Values for the maximum ˚ST and maximum p-value to be used as a threshold to filter out locality pairs with either a large genetic distance or statistically non-significant values. • A csv formatted list of the localities which were included in the genetic distance analysis. This list contained a 3 letter code for each locality, as well as it's longitude/latitude location. • Two flags to indicate if the script should use ˚ST weighting or not, and if the script should export the resulting corridor map in GeoTiff format.

The ˚ST pair-wise matrix of the 38 NWS fly localities (potentially 703 possible pairs) also included a statistical significance for each pair (p-value). Those pairs with p > 0.05 were filtered out by the script, and not included in the corridor procedure. In this analysis 200 locality pairs remained after filtering. Additionally, the actual ˚ST value for each pair was used as a weighting coefficient so that the geographic distance, together with the "environmental" distance (the hsm raster) would be enhanced by the genetic distance. The ˚ST values extend from 0 to 1, where ˚ST = 0 indicates genetically identical samples. So higher values indicate greater genetic differentiation. The weighting factor was defined to have values from 0 to 4 as

*• if (˚S T = 0) then weight coef = 4 • otherwise weight coef = log (1/˚S T ).*

Thus very small ˚ST (low genetic differentiation) got a large weight coefficient value. Whereas pairs with high ˚ST (highly differentiated) were given an exponentially decreasing weight coefficient. The value of 4 for the edge case of ˚ST = 0 was chosen as follows: since the precision of the values in the matrix was three decimal places then the minimum value above 0 would be 0.001 which, using log(1/˚S T ), got a coefficient of 3. So the values of ˚ST = 0 were given the highest coefficient of 4.

The procedure for creating migration corridors for each pair of localities took into account three parameters: the environment suitability, the geographic distance, and the genetic differentiation. First the environmental data as represented in the hsm raster was the base layer for calculating a cost raster for each of the individual points in the pair of localities. The standard "least cost path" GRASS module was used to calculate the most suitable path over the hsm raster to migrate to each locality. So, these cost rasters represented the "easiest" environmental distance over the hsm raster to reach each locality. By adding together the two cost rasters for each pair of localities in the analysis, we obtained a corridor raster showing a predicted migration path (least cost path) between the two points in each pair. This corridor reflected both environmental distance and geographic distance. The corridor raster was then weighted using a map algebra expression to divide the corridor raster by the pair's weight coefficient. We divided the corridor raster by the weight coefficient since (as explained above) larger coefficients indicate genetically closer populations. So pairs with low ˚ST values got a high coefficient, and their corridors display as "closer" or more highly connected in the final map. Finally, all corridors were merged together into one continent-wide network map.

### Results
The habitat suitability map produced for the NWS fly using Maxent is shown in Fig. 1. The "Area Under the Curve" (AUC) value obtained for this run was 0.888, indicating the high quality of model output (Elith et al., 2006;Suárez-Seoane et al., 2008;Swets, 1988). The map shows large areas of high suitability for the NWS fly in South America, distributed throughout the continent, but interrupted by low suitability areas in the Andes and Amazon regions. Interestingly, the areas near the rivers in the Amazon region showed high suitability.

We note that in Central America the country of Costa Rica displays as white, i.e. no value. This is due to the way the Maxent software processes null values in the input data. If any one of the inputs shows null values for any raster pixels, those pixels will receive a null value in the output. Indeed, the LCC data set has no values for Costa Rica, thus it caused the null values in the final habitat suitability map. Since our analysis focuses on South America, we do not consider this to detract from the conclusions.

The Maxent results indicated that the strongest predictor for habitat suitability was indeed the LCC data, and altitude was the second strongest predictor. Initially, several other candidate environment predictors were tested by repeating runs of the Maxent program with other combinations of input data. The "jackknife" routine within the Maxent algorithm (Fig. 2) drew attention to these predictors, while others had low to negligible influence on the result.

The pairwise ˚ST matrix of the 38 NWS fly localities showed 200 significant values among the 703 possible pairs (Table S3); as thresholds for corridors construction an ˚ST maximum of 0.25 and p-value of 0.05 were used. Thus, pairs of localities with pairwise ˚ST > 0.25 or p-value > 0.05 were filtered out by the script and no connection corridors were plotted. Fig. 3 shows the results for the NWS fly corridors in South America. The region alongside the Atlantic Ocean shows the stronger connectivity between the north of Amazon region (NAG) and the south (SAG), being the region of probable migration. The region through the Northwest of Brazil and Peru also appears as a likely corridor of probable migration between NAG and SAG. Even though all the NWS fly sampled localities in South America showed some degree of connection, the populations within NAG are structured showing low to medium connectivity, and the populations within SAG are not structured showing medium to high connectivity. In the Amazon region, the sampling localities present medium connectivity that could be interpreted as a resistance of the forest to NWS fly migration (for a discussion see Mastrangelo et al., 2014).

### Discussion
Our approach integrates genetic and environmental data within a GIS to map the connection corridors between the NWS fly sampling localities. The results show a good correlation with current understanding of the species migration in South America (for discussion see Lyra et al., 2009;Fresia et al., 2011Fresia et al., , 2013)). This match between assumed movement of the insect, and the resulting corridor map increases our confidence in the validity of the procedure. Furthermore, each of the three components of the method outlined above: genetic differentiation, habitat suitability, and least cost path analysis is flexible. Many adjustments and calibrations can be applied to adapt the procedure to differing circumstances and other species. We hope therefore that other researchers will adopt the method, and report similar encouraging results.

The map obtained with Maxent depicts the main NWS fly requirements and shows that the high suitability areas detected are coincident with the most important livestock breeding regions in the continent. Nevertheless, some bias is introduced because most of the 134 geo-referenced NWS fly observations were in livestock breeding regions. Yet we did not observe an over-fitting of the model (Maxent regularization parameter = 2) and in addition some low suitability areas were predicted for geo-referenced observations (see Fig. 1).

The probable migration corridors illustrated by our GIS approach could be the effect of the Andes region structuring NWS fly populations on each side. Furthermore the populations of SAG went through a recent population expansion that blurred the phylogeographic structure (for a discussion see Fresia et al., 2011Fresia et al., , 2013)). This genetic diversity distribution could have been produced due to livestock introduction in the Americas about 500 years ago, with Argentina, Brazil, Paraguay and Uruguay having the highest livestock numbers in the continent. Animal movement could surely have helped to augment this distribution pattern with no clear geographic structure.

This integrative approach could be adopted by any AW-IPM, thus enhancing the understanding of the migration routes of an insect to help in the selection of target regions for treatment. An AW-IPM employing SIT to reduce insect populations could strongly benefit from this approach in a region like South America. The SIT method is particularly efficient at low population densities. Thus it is extremely important to be in a position to identify confined or isolated populations, as well as connection corridors between them, in order to delineate target areas for control. An analysis of migration corridors will assist in the design of a more efficient and effective AW-IPM based on SIT, helping to make it viable in large geographic regions with different biomes. To achieve this aim, we also propose three future improvements to refine the method: defining a high resolution geographic analysis in the NWS fly sampling strategy, adding other variables in the niche modelling simulations (such as livestock distribution), and applying a population genomics approach. The improvement of the species distribution map and the inclusion of nuclear markers would increase our ability to detect the geographic structure of the NWS fly, and help to infer more precise and narrower migration corridors.


### Acknowledgements

We would like to thank the guest editor of this special number and three anonymous reviewers, whose suggestions and comments significantly improved the manuscript. This work was supported by research contracts RE-14844-RO and 14856-RO from FAO/IAEA CRP: Applying Population Genetics and GIS for Managing Livestock Insect Pests, and the Fundac ¸ ão de Amparo à Pesquisa do Estado de São Paulo (FAPESP) project 2012/11654-9. Open source software tools were employed extensively in this research, notably The Geographic Resources Analysis Support System (GRASS), Arlequin, Maxent and the Geospatial Data Abstraction Library (GDAL). We thank the developers for making the tools available to the scientific community.

14856-RO
GIS for Managing Livestock Insect Pests
FAO/IAEA CRP: Applying Population Genetics


2012/11654-9

### Appendix A. Supplementary data

Supplementary data associated with this article can be found, in the online version, at http://dx.doi.org/10.1016/ j.actatropica.2014.04.003


## References
**[1]** A comparison shopper's guide to connectivity metrics *J Calabrese and W Fagan* *Front. Ecol. Environ* (2004) 2.
**[2]** Datos obtenidos a partir de una encuesta relativo a la incidencia de miasis cutáneas en diferentes zonas del Uruguay *M Carballo et al.* *Veterinaria* (1991) 28.
**[3]** Integrating statistical genetic and geospatial methods brings new power to phylogeography *L Chan et al.* *Mol. Phylogenet. Evol* (2011) 59.
**[4]** Current status of the New World Screwworm Cochliomyia hominivorax in Venezuela *A Coronado and A Kowalski* *Med. Vet. Entomol* (2009) 23.
**[5]** Novel methods improve prediction of species' distributions from occurrence data *J Elith et al.* *Ecography* (2006) 29.
**[6]** Arlequin suite ver 3.5: a new series of programs to perform population genetics analyses under Linux and Windows *L Excoffier and H Lischer* *Mol. Ecol. Res* (2010) 10.
**[7]** Analysis of molecular variance inferred from metric distances among DNA haplotypes: application to human mitochondrial DNA restriction data *L Excoffier et al.* *Genetics* (1992) 131.
**[8]** Landscape modification and habitat fragmentation: a synthesis *J Fischer and D Lindenmayer* *Global Ecol. Biogeogr* (2007) 16.
**[9]** Genetic structure and demographic history of new world screwworm across its current geographic range *P Fresia et al.* *J. Med. Entomol* (2011) 48.
**[10]** The phylogeographic history of the new world screwworm fly. Inferred by approximate Bayesian computation analysis *P Fresia et al.* *PLoS One* (2013) 8 (10) pp. 76168 https://doi.org/10.1371/journal.pone.0076168 [dx.doi.org](http://dx.doi.org/10.1371/journal.pone.0076168) [dx.doi.org](http://dx.doi.org/10.1371/journal.pone.0076168).
**[11]** Insecticidal wound treatment of livestock on Isla de la Juventud, Cuba: an efficient suppression method of New World screwworm Cochliomyia hominivorax prior to the release of sterile insect *R Garcia et al.* (2007) https://doi.org/10.1371/journal.pone.0076168.
**[12]** GDAL -Geospatial Data Abstraction Library: Version x.x.x, Open Source Geospatial Foundation *Gdal* (2014) [//bioval.jrc.ec.europa.eu/products/glc2000/glc2000.php](//bioval.jrc.ec.europa.eu/products/glc2000/glc2000.php) [//bioval.jrc.ec.europa.eu/products/glc2000/glc2000.php](//bioval.jrc.ec.europa.eu/products/glc2000/glc2000.php).
**[13]** Screwworm eradication program: a review of recent mass-rearing technology Southwest *J Goodenough et al.* *Entomology* (1983) 8.
**[14]** Geographic Resources Analysis Support System (GRASS) Software. Open Source Geospatial Foundation Project (2012) [grass.osgeo.org](http://grass.osgeo.org) [grass.osgeo.org](http://grass.osgeo.org).
**[15]** The new world screwworm: prospective distribution and role of weather in eradication *A Gutierrez and L Ponti* *Agric. For. Entomol* (2014) https://doi.org/10.1111/afe [dx.doi.org](http://dx.doi.org/10.1111/afe) [dx.doi.org](http://dx.doi.org/10.1111/afe).
**[16]** Principles of Population Genetics *D Hartl and A Clark* (1997) https://doi.org/10.1111/afe.
**[17]** Population dynamics of the screwworm fly, Cochliomyia hominivorax (Coquerel), with respect to control by the sterile-male technique *B Hightower* *Insect Ecology and the Sterile-Male Technique* (1969).
**[18]** Seasonal abundance of the screw-worm in Northern Mexico *B Hightower et al.* *J. Econ. Entomol* (1966) 2.
**[19]** Phylogeography's past, present, and future: 10 years after Avise *M Hickerson et al.* *Mol. Phylogenet* (2010) 54.
**[20]** Estimation of levels of gene flow from DNA sequence data *R Hudson et al.* *Genetics* (1992) 132.
**[21]** Phylogeographic information systems: putting the geography into phylogeography *D Kidd and M Ritchie* *J. Biogeogr* (2006) 33.
**[22]** The coalescent. Stoch. Processes Appl *J Kingman* *The coalescent. Stoch. Processes Appl* (1982) 13.
**[23]** Sterile Insect Technique: Principles and Practice in Area-wide Integrated Pest Management *W Klassen and C Curtis* (2005).
**[24]** Statistical phylogeography *L Knowles* *Annu. Rev. Ecol. Evol. Syst* (2009) 40.
**[25]** Integrating GIS-based environmental data into evolutionary biology *K Kozak et al.* *Trends Ecol. Evol* (2008) 23.
**[26]** Coalescent genealogy samplers: windows into population history *M Kuhner* *Trends Ecol. Evol* (2008) 24.
**[27]** Overwintering of Cochliomyia americana at *A Lindquist and W Barrett* *J. Econ. Entomol* (1945) 38.
**[28]** Complex pattern of genetic distribution in populations of the NewWorld screwworm fly revealed by mitochondrial DNA markers *M Lyra et al.* *Med. Vet. Entomol* (2009) 23.
**[29]** Habitat preferences and dispersal patterns in native screwworm fly (Diptera: Calliphoridae) *R Mangan and D Thomas* *Ann. Entomol. Soc. Am* (1989) 82.
**[30]** Genetic diversity and population structure of the New World screwworm from the Amazon basin *T Mastrangelo et al.* *Acta Trop* (2014) 138.
**[31]** Statistical inferences in phylogeography *R Nielsen and M Beaumont* *Mol. Ecol* (2009) 18.
**[32]** Influence of habitat, season and attractant on adult behavior of the screwworm (Diptera: Calliphoridae) inatropical dry zone in Costa Rica *F Parker et al.* *J. Econ. Entomol* (1993) 86.
**[33]** Effect of weather on Cochliomyia americana and a review of methods and economic applications of the study *D Parman* *J. Econ. Entomol* (1945) 38.
**[34]** Seasonal and spatial and distributions of adult Screwworms (Diptera: Calliphoridae) in the Panama Canal Area, Republic of Panama *P Phillips et al.* *J. Med. Entomol* (2004) 41.
**[35]** Maximum entropy modeling of species geographic distributions *S Phillips et al.* *Ecol. Modell* (2006) 190.
**[36]** Distribution modelling and statistical phylogeography: an integrative framework for generating and testing alternative biogeographical hypotheses *C Richards et al.* *J. Biogeogr* (2007) 34.
**[37]** The role of molecular genetics in sculpting the future of integrative biogeography *B Riddle et al.* *Prog. Phys. Geogr* (2008) 32.
**[38]** Determination of a relationship between soil-moisture and screwworm fly (Diptera Calliphoridae) activity *M Stuart et al.* *Aust. J. Entomol* (1995) 34.
**[39]** Maximum entropy niche-based modelling of seasonal changes in little bustard (Tetrax tetrax) distribution *S Suárez-Seoane et al.* *Ecol. Modell* (2008) 219.
**[40]** Measuring the accuracy of diagnostic systems *J Swets* *Science* (1988) 240.
**[41]** Impact of screwworm eradication programmes using the sterile insect technique *M Vargas-Teran et al.* (2005).
**[42]** Evolution in Mendelian populations *S Wright* *Genetics* (1931) 16.
