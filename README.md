# nested
Multidimentional and inexpensive data format



## <a name="data_types"></a>Data types
* i: int
* f: float
* b: bool
* s: string

## Headers format

### Metadata:
```
»id║field_1║field_2║field_3║...║field_M
```
- id: Register identifier
- field_M: Any additional field that is not going to be shown

### Levels:
```
╚level╬id╬open╬type╬name╬label╬description╬default╚...sublevels...
```
- level: Category level number [0,...]
- id: Identifier of the category. Unique value, could be integer or string
- open: If will be show as open by default [t, f]
- type: Available [data types](#data_types)
- name: Category name
- label: Category label to show
- description: A description to show the user when interact with the category
- default: default value for the data in this category
- sublevels: Children categories

## Data format
```
└level┼id┼value
```
- level: Category level number [0,...]
- id: Identifier of the category
- value: Value for the register in the level and category

## Examples:
**Level 1:**
* plain:
```
╚1╬1╬i╬meter╬Meter╬╬0╚2╬3╬i╬centi╬Centimeter╬╬0╚3╬4╬i╬milli╬Millimeter╬╬0╚N╬5╬i╬other╬Other╬╬0╚N╬6╬i╬another╬Another╬╬0╚1╬2╬i╬meter╬Meter╬╬0╚2╬3╬i╬centi╬Centimeter╬╬0╚3╬4╬i╬milli╬Millimeter╬╬0╚N╬5╬i╬other╬Other╬╬0╚N╬6╬i╬another╬Another╬╬0
```
* indented:
```
      ╚1╬1╬i╬meter╬Meter╬╬0
        ╚2╬3╬i╬centi╬Centimeter╬╬0
          ╚3╬4╬i╬milli╬Millimeter╬╬0
            ╚N╬5╬i╬other╬Other╬╬0
            ╚N╬6╬i╬another╬Another╬╬0
      ╚1╬2╬i╬meter╬Meter╬╬0
        ╚2╬3╬i╬centi╬Centimeter╬╬0
          ╚3╬4╬i╬milli╬Millimeter╬╬0
            ╚N╬5╬i╬other╬Other╬╬0
            ╚N╬6╬i╬another╬Another╬╬0
```

**Level 2:**
* plain:
```
╚2╬3╬i╬centi╬Centimeter╬╬0╚3╬4╬i╬milli╬Millimeter╬╬0╚N╬5╬i╬other╬Other╬╬0╚N╬6╬i╬another╬Another╬╬0
```
* indented:
```
      ╚2╬3╬i╬centi╬Centimeter╬╬0
        ╚3╬4╬i╬milli╬Millimeter╬╬0
          ╚N╬5╬i╬other╬Other╬╬0
          ╚N╬6╬i╬another╬Another╬╬0
```

**Level 3:**
* plain:
```
╚3╬4╬i╬milli╬Millimeter╬╬0╚N╬5╬i╬other╬Other╬╬0╚N╬6╬i╬another╬Another╬╬0
```
* indented:
```
      ╚3╬4╬i╬milli╬Millimeter╬╬0
        ╚N╬5╬i╬other╬Other╬╬0
        ╚N╬6╬i╬another╬Another╬╬0
```

**Level N:**
```
╚N╬5╬i╬other╬Other╬╬0
```

**Level 1 with Metadata:**
* plain:
```
»id║color║height║width╚1╬1╬i╬meter╬Meter╬╬0╚2╬3╬i╬centi╬Centimeter╬╬0╚3╬4╬i╬milli╬Millimeter╬╬0╚N╬5╬i╬other╬Other╬╬0╚N╬6╬i╬another╬Another╬╬0╚1╬2╬i╬meter╬Meter╬╬0╚2╬3╬i╬centi╬Centimeter╬╬0╚3╬4╬i╬milli╬Millimeter╬╬0╚N╬5╬i╬other╬Other╬╬0╚N╬6╬i╬another╬Another╬╬0
```
* indented:
```
      »id║color║height║width
      ╚1╬1╬i╬meter╬Meter╬╬0
        ╚2╬3╬i╬centi╬Centimeter╬╬0
          ╚3╬4╬i╬milli╬Millimeter╬╬0
            ╚N╬5╬i╬other╬Other╬╬0
            ╚N╬6╬i╬another╬Another╬╬0
      ╚1╬2╬i╬meter╬Meter╬╬0
        ╚2╬3╬i╬centi╬Centimeter╬╬0
          ╚3╬4╬i╬milli╬Millimeter╬╬0
            ╚N╬5╬i╬other╬Other╬╬0
            ╚N╬6╬i╬another╬Another╬╬0
```

=============================================================
## Data format


```
└level┼id┼value
```
Example:
```
└3┼2┼80
```


-- 8.283.827 caracteres

»
†
‡
«
|
¦
µ
ǁ
ǂ
Ͱ
╟

HEADERS:
	Register:



	Level1:
		╠id═type═name═label═default┣subcategory1├field11├field12┣subcategory2├field21├field22
		i.e.
			Categoría:
			╠1═utilizacion══desplegar┣1╍ideal╍╍2512000├1╌ideal╌╌2512000┣2╍programmed╍╍1942000├2╌programacion╌╌1942000
				Indentada:
				╠1═utilizacion══desplegar
					┣1╍ideal╍╍2512000
						├1╌ideal╌╌2512000
					┣2╍programmed╍╍1942000
						├2╌programacion╌╌1942000

	Subcategories:
		┣id╍name╍label╍value├field1├field2├...
		i.e.
			Subcategoría:
			┣1╍ideal╍╍2512000├1╌ideal╌╌2512000
				Indentada:
				┣1╍ideal╍╍2512000
					├1╌ideal╌╌2512000

			Subcategoría:
			┣2╍programmed╍╍1942000├2╌programacion╌╌1942000
				Indentada:
				┣2╍programmed╍╍1942000
					├2╌programacion╌╌1942000


	Fields:
		├id╌type╌name╌label╌default
		i.e.
			├5╌integer╌plate╌Placa╌WCM248
			├1╌ideal╌╌2512000
			├2╌programacion╌╌1942000




DATA:

	Register:
		[id] => 24
        [bag_id] => 16
        [fleet_id] => 3
        [taxi_bag_label] => 2013 Segundo semestre
        [total_days] => 31
        [city_name] => Bogotá


	Categories:
		╠id═name═label═value┣subcategory1├field11├field12┣subcategory2├field21├field22
		i.e.
			Categoría:
			╠1═utilizacion══desplegar┣1╍ideal╍╍2512000├1╌ideal╌╌2512000┣2╍programmed╍╍1942000├2╌programacion╌╌1942000
				Indentada:
				╠1═utilizacion══desplegar
					┣1╍ideal╍╍2512000
						├1╌ideal╌╌2512000
					┣2╍programmed╍╍1942000
						├2╌programacion╌╌1942000

	Subcategories:
		┣id╍name╍label╍value├field1├field2├...
		i.e.
			Subcategoría:
			┣1╍ideal╍╍2512000├1╌ideal╌╌2512000
				Indentada:
				┣1╍ideal╍╍2512000
					├1╌ideal╌╌2512000

			Subcategoría:
			┣2╍programmed╍╍1942000├2╌programacion╌╌1942000
				Indentada:
				┣2╍programmed╍╍1942000
					├2╌programacion╌╌1942000


	Fields:
		├id╌name╌label╌value
		i.e.
			├5╌plate╌Placa╌WCM248
			├1╌ideal╌╌2512000
			├2╌programacion╌╌1942000
