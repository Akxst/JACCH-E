
## energy-perspective-2025-2030-germany

This is a repository containing a scenario that implements the market for energy in Germany and its projections 2025, 2030 report for:

 - electricity,
 - heat.

It is meant to be used in premise in addition to a global IAM scenario, to provide refined projections at the country level.

This data package contains all the files necessary for premise to implement this scenario and create market-specific composition for electricity and heat.


### Ecoinvent database compatibility
ecoinvent 3.8 cut-off

How to use it:

```python

import brightway2 as bw
from premise import NewDatabase
from datapackage import Package
    
    
fp = r"C:/Users/conlod/Autumn_school/heat_Germany_20_25_30/datapackage.json"
heat = Package(fp)
    
ndb = NewDatabase(
            scenarios = [
                {"model":"remind", "pathway":"SSP2-Npi", "year":2020,},
                {"model":"remind", "pathway":"SSP2-Npi", "year":2025,},
                {"model":"remind", "pathway":"SSP2-Npi", "year":2030,},
            ],        
            source_db="ei_3.8_cutoff",
            source_version="3.8",
            key= 'tUePmX_S5B8ieZkkM7WUU2CnO8SmShwmAeWK9x2rTFo=',
            external_scenarios=[
                heat, # <-- list datapackage objects here
            ] 
        )
        
        
```
