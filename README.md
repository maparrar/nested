# nested
Multidimentional and inexpensive data format



## <a name="data_types"></a>Data types
* i: int
* f: float
* b: bool
* s: string

## Headers format

### Levels:
```
~level|id|visible|open|type|name|label|description|default~...children...
```
- level: Category level number [0,...]
- id: Identifier of the category. Unique value, could be integer or string
- visible: If will be show [0: invisible, 1: visible]
- open: If will be show as open by default [0: closed, 1: opened]
- type: Available [data types](#data_types)
- name: Category name
- label: Category label to show
- description: A description to show the user when interact with the category
- default: default value for the data in this category
- children: Children categories

## Data format
```
├record_id¬level^cat_id^value¬level^cat_id^value
```
- record_id: Record identifier
- level: Category level number [0,...]
- cat_id: Identifier of the category
- value: Value for the register in the level and category

## Examples:
**Level 1:**
* plain:
```
~0|1|t|t|i|meter|Meter||0~1|3|t|t|i|centi|Centimeter||0~2|4|t|t|i|milli|Millimeter||0~N|5|t|t|i|other|Other||0~N|6|t|t|i|another|Another||0~0|2|t|t|i|meter|Meter||0~1|3|t|t|i|centi|Centimeter||0~2|4|t|t|i|milli|Millimeter||0~N|5|t|t|i|other|Other||0~N|6|t|t|i|another|Another||0
```
* indented:
```
      ~0|1|t|t|i|meter|Meter||0
        ~1|3|t|t|i|centi|Centimeter||0
          ~2|4|t|t|i|milli|Millimeter||0
            ~N|5|t|t|i|other|Other||0
            ~N|6|t|t|i|another|Another||0
      ~0|2|t|t|i|meter|Meter||0
        ~1|3|t|t|i|centi|Centimeter||0
          ~2|4|t|t|i|milli|Millimeter||0
            ~N|5|t|t|i|other|Other||0
            ~N|6|t|t|i|another|Another||0
```

**Level 2:**
* plain:
```
~1|3|t|t|i|centi|Centimeter||0~2|4|t|t|i|milli|Millimeter||0~N|5|t|t|i|other|Other||0~N|6|t|t|i|another|Another||0
```
* indented:
```
      ~1|3|t|t|i|centi|Centimeter||0
        ~2|4|t|t|i|milli|Millimeter||0
          ~N|5|t|t|i|other|Other||0
          ~N|6|t|t|i|another|Another||0
```

**Level 3:**
* plain:
```
~2|4|t|t|i|milli|Millimeter||0~N|5|t|t|i|other|Other||0~N|6|t|t|i|another|Another||0
```
* indented:
```
      ~2|4|t|t|i|milli|Millimeter||0
        ~N|5|t|t|i|other|Other||0
        ~N|6|t|t|i|another|Another||0
```

**Level N:**
```
~N|5|t|t|i|other|Other||0
```

**Level 1 with data:**
* plain:
```
~0|1|t|t|i|meter|Meter||0~1|3|t|t|i|centi|Centimeter||0~2|4|t|t|i|milli|Millimeter||0~N|5|t|t|i|other|Other||0~N|6|t|t|i|another|Another||0~0|2|t|t|i|meter|Meter||0~1|3|t|t|i|centi|Centimeter||0~2|4|t|t|i|milli|Millimeter||0~N|5|t|t|i|other|Other||0~N|6|t|t|i|another|Another||0├123¬0^1^qweA¬1^2^ertA''¬2^4^tyuA¬N^5^zxcA¬N^6^dfsA¬0^2^qweA¬1^3^ertA¬2^4^tyuA¬N^5^zxcA¬N^6^dfsA├124¬0^1^qweB¬1^2^erB¬2^4^tyuB¬N^5^zxcB¬N^6^dfsB├125¬0^1^qweC¬1^2^erC¬2^4^tyuC¬N^5^zxcC¬N^6^dfsC¬0^2^qweC¬1^3^erC¬2^4^tyuC¬N^5^zxcC¬N^6^dfsC
```
* indented:
```
      # Headers
      ~0|1|t|t|i|meter|Meter||0
        ~1|3|t|t|i|centi|Centimeter||0
          ~2|4|t|t|i|milli|Millimeter||0
            ~N|5|t|t|i|other|Other||0
            ~N|6|t|t|i|another|Another||0
      ~0|2|t|t|i|meter|Meter||0
        ~1|3|t|t|i|centi|Centimeter||0
          ~2|4|t|t|i|milli|Millimeter||0
            ~N|5|t|t|i|other|Other||0
            ~N|6|t|t|i|another|Another||0
      # Data
      ├123
      ¬0^1^qweA
        ¬1^2^ertA
          ¬2^4^tyuA
            ¬N^5^zxcA
            ¬N^6^dfsA
      ¬0^2^qweA
        ¬1^3^ertA
          ¬2^4^tyuA
            ¬N^5^zxcA
            ¬N^6^dfsA
      ├124
      ¬0^1^qweB
        ¬1^2^erB
          ¬2^4^tyuB
            ¬N^5^zxcB
            ¬N^6^dfsB
      ├125
      ¬0^1^qweC
        ¬1^2^erC
          ¬2^4^tyuC
            ¬N^5^zxcC
            ¬N^6^dfsC
      ¬0^2^qweC
        ¬1^3^erC
          ¬2^4^tyuC
            ¬N^5^zxcC
            ¬N^6^dfsC
```





~0|1|1|0|i|level0_cat1|Level0_cat1|Level0_cat1|
~0|1|1|0|i|level1_cat1|Level1_cat1|Level1_cat1|
~0|1|1|0|b|level3_cat1|Level3_cat1|Level3_cat1|
~0|2|1|0|s|level1_cat2|Level1_cat2|Level1_cat2|


~0|1|1|0|i|level0_cat1|Level0_cat1|Level0_cat1|
~0|1|1|0|i|level1_cat1|Level1_cat1|Level1_cat1|
~0|1|1|0|b|level3_cat1|Level3_cat1|Level3_cat1|
~0|2|1|0|s|level1_cat2|Level1_cat2|Level1_cat2|


~0|1|1|0|i|level0_cat1|Level0_cat1|Level0_cat1|
	~1|1|1|0|i|level1_cat1|Level1_cat1|Level1_cat1|
		~2|1|1|0|b|level3_cat1|Level3_cat1|Level3_cat1|
	~1|2|1|0|s|level1_cat2|Level1_cat2|Level1_cat2|



~0|1|1|0|i|level0_cat1|Level0_cat1|Level0_cat1|
	~1|1|1|0|i|level1_cat1|Level1_cat1|Level1_cat1|
		~2|1|1|0|b|level3_cat1|Level3_cat1|Level3_cat1|
	~1|2|1|0|s|level1_cat2|Level1_cat2|Level1_cat2|
~0|2|1|0|i|level0_cat2|Level0_cat2|Level0_cat2|
	~1|8|1|0|i|level1_cat8|Level1_cat8|Level1_cat8|
		~2|9|1|0|b|level3_cat9|Level3_cat9|Level3_cat9|
	~1|10|1|0|s|level1_cat10|Level1_cat10|Level1_cat10|


~0|1|1|0|i|level0_cat1|Level0_cat1|Level0_cat1|
	~1|1|1|0|i|level1_cat1|Level1_cat1|Level1_cat1|
		~2|1|1|0|b|level3_cat1|Level3_cat1|Level3_cat1|
	~1|2|1|0|s|level1_cat2|Level1_cat2|Level1_cat2|
~0|2|1|0|i|level0_cat2|Level0_cat2|Level0_cat2|
	~1|8|1|0|i|level1_cat8|Level1_cat8|Level1_cat8|
		~2|9|1|0|b|level3_cat9|Level3_cat9|Level3_cat9|
			~3|15|1|0|b|level3_cat15|Level3_cat15|Level3_cat15|
	~1|10|1|0|s|level1_cat10|Level1_cat10|Level1_cat10|


~0|1|1|0|i|level0_cat1|Level0_cat1|Level0_cat1|2
	~1|1|1|0|i|level1_cat1|Level1_cat1|Level1_cat1|
		~2|1|1|0|b|level3_cat1|Level3_cat1|Level3_cat1|
	~1|2|1|0|s|level1_cat2|Level1_cat2|Level1_cat2|2
~0|2|1|0|i|level0_cat2|Level0_cat2|Level0_cat2|
	~1|8|1|0|i|level1_cat8|Level1_cat8|Level1_cat8|
		~2|9|1|0|b|level3_cat9|Level3_cat9|Level3_cat9|
			~3|15|1|0|b|level3_cat15|Level3_cat15|Level3_cat15|
	~1|10|1|0|s|level1_cat10|Level1_cat10|Level1_cat10|

¬10001^0^1^50001
¬10002^1^1^50002
¬10003^3^1^50003
