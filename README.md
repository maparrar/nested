# nested
Multidimentional and inexpensive data format




## Headers format



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
		»[id] => 24
        [bag_id] => 16
        [fleet_id] => 3
        [taxi_bag_label] => 2013 Segundo semestre
        [total_days] => 31
        [city_name] => Bogotá


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
