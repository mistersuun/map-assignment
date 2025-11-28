# Data Sources

This document describes the data sources used in the SmartAgri web mapping project.

## Important Note

The GeoJSON data files in this project contain **sample/demonstration data** created for educational purposes. While the locations and organizations referenced are real, the exact coordinates and some details have been approximated or simplified for demonstration purposes.

**For production use, official data sources should be consulted.**

---

## Markets & CSA (`data/markets_csa.geojson`)

**18 features** (11 Markets, 7 CSA drop-offs)

### Data References:
- **Marchés Publics de Montréal**: https://www.marchespublics-mtl.com/
  - Jean-Talon, Atwater, Maisonneuve, Lachine markets
- **Marché du Vieux-Port de Québec**: https://www.marchevieuxport.com/
- **Équiterre (CSA network)**: https://www.equiterre.org/
  - CSA drop-off locations based on Équiterre's network
- **Ferme des Quatre-Temps**: https://fermequatretemps.ca/

### Official Data Sources for Real Projects:
- **MAPAQ (Ministère de l'Agriculture)**: https://www.mapaq.gouv.qc.ca/
- **Équiterre CSA Directory**: https://www.equiterre.org/projet/fermiers-de-famille
- **Marchés Publics du Québec**: https://www.ampq.ca/

---

## Food Access Sites (`data/food_access.geojson`)

**18 features** (Food banks, community fridges, community kitchens, shelters)

### Data References:
- **Moisson Montréal**: https://www.moissonmontreal.org/
- **Moisson Québec**: https://www.moissonquebec.com/
- **Sun Youth Organization**: https://sunyouthorg.com/
- **NDG Food Depot**: https://www.depotndg.org/
- **Santropol Roulant**: https://santropolroulant.org/
- **MultiCaf**: https://www.multicaf.org/
- **Welcome Hall Mission**: https://welcomehallmission.com/
- **Dans la rue**: https://danslarue.org/
- **Maison du Père**: https://maisondupere.org/
- **Community Fridges Montreal**: Locations based on known community fridge initiatives

### Official Data Sources for Real Projects:
- **Banques alimentaires du Québec**: https://www.banquesalimentaires.org/
- **Centraide/United Way**: https://www.centraide-mtl.org/
- **211 Québec (Community Services Directory)**: https://www.211qc.ca/

---

## SLC Quebec / Agricultural Zones (`data/slc_quebec.geojson`)

**8 features** (5 agricultural region polygons, 3 farm point locations)

### Data References:
- Agricultural regions based on Quebec's administrative regions:
  - Montérégie, Lanaudière, Centre-du-Québec, Laval, Île d'Orléans
- Farm locations:
  - **Ferme Cadet Roussel**: https://www.fermecadetroussel.org/
  - **Les Jardins de la Grelinette**: https://lagrelinette.com/
  - **Ferme des Quatre-Temps**: https://fermequatretemps.ca/

### Official Data Sources for Real Projects:
- **CPTAQ (Commission de protection du territoire agricole)**: https://www.cptaq.gouv.qc.ca/
- **Données Québec (Open Data Portal)**: https://www.donneesquebec.ca/
- **Financière agricole du Québec**: https://www.fadq.qc.ca/

---

## Soil Suitability (`data/soil_suitability_quebec.geojson`)

**1042 polygon features** with suitability ratings (H=High, M=Medium, L=Low)

### Official Data Source:

**Soil Landscapes of Canada (SLC) Version 3.2**
- **Publisher**: Agriculture and Agri-Food Canada
- **Open Data Portal**: https://open.canada.ca/data/en/dataset/5ad5e20c-f2bb-497d-a2a2-440eec6e10cd
- **Direct Download**: https://agriculture.canada.ca/atlas/data_donnees/soilLandscapesOfCanada3_2/data_donnees/geojson/soil_landscapes_of_canada_v3r2_geojson.zip
- **License**: Open Government Licence - Canada

### Processing Applied:
1. Downloaded full Canada SLC v3.2 GeoJSON dataset (~114MB)
2. Extracted polygons within Quebec agricultural region (lat 45-48, lon -79.5 to -64)
3. Assigned H/M/L suitability based on geographic agricultural potential:
   - **High (H)**: Southern Quebec lowlands (Montérégie, south shore)
   - **Medium (M)**: Central agricultural belt
   - **Low (L)**: Northern regions, Canadian Shield proximity
4. Reduced coordinate precision to 4 decimal places for file size optimization

### Suitability Distribution:
- High: 145 polygons
- Medium: 483 polygons
- Low: 414 polygons

### Additional Official Data Sources:
- **IRDA (Institut de recherche et de développement en agroenvironnement)**: https://www.irda.qc.ca/
- **Agriculture and Agri-Food Canada - SLC Documentation**: https://sis.agr.gc.ca/cansis/nsdb/slc/index.html
- **Natural Resources Canada - GeoGratis**: https://geogratis.gc.ca/

---

## Recommended Official Data Sources

For a production version of this application, consider using these official Quebec/Canadian open data sources:

| Dataset | Source | URL |
|---------|--------|-----|
| Agricultural land use | Données Québec | https://www.donneesquebec.ca/ |
| Protected agricultural zones | CPTAQ | https://www.cptaq.gouv.qc.ca/ |
| Soil data | AAFC/IRDA | https://sis.agr.gc.ca/ |
| Food banks | Banques alimentaires QC | https://www.banquesalimentaires.org/ |
| Community services | 211 Québec | https://www.211qc.ca/ |
| Farm locations | MAPAQ | https://www.mapaq.gouv.qc.ca/ |

---

## License & Attribution

- Sample data created for educational/demonstration purposes
- Real organization names and websites are used for reference
- Actual coordinates are approximations
- For official use, verify data with original sources

**Project created as part of a university web mapping course.**
