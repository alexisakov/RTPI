# Tutorials for Hard Numbers: Open Consumer Price Database

Cite as:

Isakov, A., Latypov, R., Repin, A., Postolit, E., Evseev, A. and Sinelnikova-Muryleva, E. (2021). Hard Numbers: Open Consumer Price Database. Russian Journal of Money and Finance, 80(1), pp. 104–119

Database description: https://rjmf.econs.online/en/2021/1/open-consumer-price-database/


# Data Tables
## rtpi_product_properties
Fields are
| Field name | Description |
|:----------:|:-----------|
| web_price_id | id of a product to which a property corresponds |
| date_modified | time when a property was changed. The entry appears when a property is first added or when it is modified |
| properties | string representing a dict whose 'key': 'value' pairs are 'property_alias': 'property_value' |

Example
| web_price_id | date_modified | properties |
|:------------:|:-------------:|:----------:|
|3400351       | 2021-11-09 00:00:00| '{"nw":"0.01кг", "gw":"0.01кг", "pp":"шт"}'

Property aliases
| Alias | Full name | Description | Values example 
|:------|:----------|:------------|:--------------|
| ps | package size | float or int number representing the size of a package | 2, 200, 0.7, ... | 
| mu | measuring unit | measuring unit of a package size | кг, г, л, шт (штука), ... |  
| pp | price per | this field answers the question "which unit is the price for in the rtpi_price table?" | шт (штука), уп (упаковка), кг, л,...
| nw | net weight (масса нетто) | weight of a product minus package weight | 0.1кг, 200г, 500мл, ...
| gw | gross weight (масса брутто) | weight of a product including package (масса брутто) | 0.1кг, 200г, 500мл, ...

Note fields package size/measuring unit and net weight/gross weight are often about the same thing, so that the information in them may be mutually exclusive. An exception might be when, for example, in a wholesale store you should buy many items at once (the box with 10 bottles of water, 5 packages of cottage cheese, etc). In that case the pair package size/measuring unit represents the size of a box, when a pair net weight/gross weight is about a spesific item inside this box.
