## Test: Tour Radius 1.0
willschm
### Request:
```
{

"requestType": "tour",

"earthRadius": 1.0,

"response": 0.6,

"places": [

{

"name": "Taedonggang Brewing Company",

"municipality": "Pyongyang",

"region": "East Asia",

"country": "Democratic People's Republic of Korea",

"latitude": "38.994487",

"longitude": "125.806860"

},

{

"name": "Costa Rica Meadery",

"municipality": "Heredia",

"region": "Central America",

"country": "Costa Rica",

"latitude": "10.00236",

"longitude": "-84.11651"

},

{

"name": "Anheuser-Busch InBev",

"municipality": "Leuven",

"region": "Northwestern Europe",

"country": "Belgium",

"latitude": "50.66268478322371",

"longitude": "5.621204211509651"

},

{

"name": "Ganda Geleee",

"municipality": "Kisangani",

"region": "Central Africa",

"country": "Democratic Republic of the Congo",

"latitude": "0.525303",

"longitude": "25.219764"

},

{

"name": "Salty Bear Brewing",

"municipality": "Costa Mesa",

"region": "California",

"country": "United States of America",

"latitude": "33.68198",

"longitude": "-117.92125"

},

{

"name": "Other Half Brewing",

"municipality": "New York",

"region": "New York",

"country": "United States of America",

"latitude": "40.757793",

"longitude": "-73.978729"

},

{

"name": "Goose Island Beer Co.",

"municipality": "Chicago",

"region": "Illinois",

"country": "United States of America",

"latitude": "41.887101",

"longitude": "-87.672745"

},

{

"name": "Hackensack Brewing",

"municipality": "Hackensack",

"region": "New Jersey",

"country": "United States of America",

"latitude": "40.90348",

"longitude": "-74.04084"

}

]

}
```
### T45 Response:
```
{

"places": [

{

"name": "Taedonggang Brewing Company",

"municipality": "Pyongyang",

"region": "East Asia",

"country": "Democratic People's Republic of Korea",

"latitude": "38.994487",

"longitude": "125.806860"

},

{

"name": "Anheuser-Busch InBev",

"municipality": "Leuven",

"region": "Northwestern Europe",

"country": "Belgium",

"latitude": "50.66268478322371",

"longitude": "5.621204211509651"

},

{

"name": "Costa Rica Meadery",

"municipality": "Heredia",

"region": "Central America",

"country": "Costa Rica",

"latitude": "10.00236",

"longitude": "-84.11651"

},

{

"name": "Salty Bear Brewing",

"municipality": "Costa Mesa",

"region": "California",

"country": "United States of America",

"latitude": "33.68198",

"longitude": "-117.92125"

},

{

"name": "Goose Island Beer Co.",

"municipality": "Chicago",

"region": "Illinois",

"country": "United States of America",

"latitude": "41.887101",

"longitude": "-87.672745"

},

{

"name": "Other Half Brewing",

"municipality": "New York",

"region": "New York",

"country": "United States of America",

"latitude": "40.757793",

"longitude": "-73.978729"

},

{

"name": "Hackensack Brewing",

"municipality": "Hackensack",

"region": "New Jersey",

"country": "United States of America",

"latitude": "40.90348",

"longitude": "-74.04084"

},

{

"name": "Ganda Geleee",

"municipality": "Kisangani",

"region": "Central Africa",

"country": "Democratic Republic of the Congo",

"latitude": "0.525303",

"longitude": "25.219764"

}

],

"earthRadius": 1.0,

"response": 0.6,

"requestType": "tour"

}
```
Issue: None Found
### T13 Response:
```
{

"places": [

{

"country": "Democratic People's Republic of Korea",

"latitude": "38.994487",

"name": "Taedonggang Brewing Company",

"municipality": "Pyongyang",

"region": "East Asia",

"longitude": "125.806860"

},

{

"country": "Belgium",

"latitude": "50.66268478322371",

"name": "Anheuser-Busch InBev",

"municipality": "Leuven",

"region": "Northwestern Europe",

"longitude": "5.621204211509651"

},

{

"country": "Costa Rica",

"latitude": "10.00236",

"name": "Costa Rica Meadery",

"municipality": "Heredia",

"region": "Central America",

"longitude": "-84.11651"

},

{

"country": "United States of America",

"latitude": "33.68198",

"name": "Salty Bear Brewing",

"municipality": "Costa Mesa",

"region": "California",

"longitude": "-117.92125"

},

{

"country": "United States of America",

"latitude": "41.887101",

"name": "Goose Island Beer Co.",

"municipality": "Chicago",

"region": "Illinois",

"longitude": "-87.672745"

},

{

"country": "United States of America",

"latitude": "40.757793",

"name": "Other Half Brewing",

"municipality": "New York",

"region": "New York",

"longitude": "-73.978729"

},

{

"country": "United States of America",

"latitude": "40.90348",

"name": "Hackensack Brewing",

"municipality": "Hackensack",

"region": "New Jersey",

"longitude": "-74.04084"

},

{

"country": "Democratic Republic of the Congo",

"latitude": "0.525303",

"name": "Ganda Geleee",

"municipality": "Kisangani",

"region": "Central Africa",

"longitude": "25.219764"

}

],

"earthRadius": 1.0,

"formula": "",

"response": 0.6,

"requestType": "tour"

}
```
Issue: Correct order was returned, however the variables in the place objects is in the wrong order.
### T14 Response:
```
{

"places": [

{

"name": "Taedonggang Brewing Company",

"municipality": "Pyongyang",

"region": "East Asia",

"country": "Democratic People's Republic of Korea",

"latitude": "38.994487",

"longitude": "125.806860"

},

{

"name": "Anheuser-Busch InBev",

"municipality": "Leuven",

"region": "Northwestern Europe",

"country": "Belgium",

"latitude": "50.66268478322371",

"longitude": "5.621204211509651"

},

{

"name": "Costa Rica Meadery",

"municipality": "Heredia",

"region": "Central America",

"country": "Costa Rica",

"latitude": "10.00236",

"longitude": "-84.11651"

},

{

"name": "Salty Bear Brewing",

"municipality": "Costa Mesa",

"region": "California",

"country": "United States of America",

"latitude": "33.68198",

"longitude": "-117.92125"

},

{

"name": "Goose Island Beer Co.",

"municipality": "Chicago",

"region": "Illinois",

"country": "United States of America",

"latitude": "41.887101",

"longitude": "-87.672745"

},

{

"name": "Other Half Brewing",

"municipality": "New York",

"region": "New York",

"country": "United States of America",

"latitude": "40.757793",

"longitude": "-73.978729"

},

{

"name": "Hackensack Brewing",

"municipality": "Hackensack",

"region": "New Jersey",

"country": "United States of America",

"latitude": "40.90348",

"longitude": "-74.04084"

},

{

"name": "Ganda Geleee",

"municipality": "Kisangani",

"region": "Central Africa",

"country": "Democratic Republic of the Congo",

"latitude": "0.525303",

"longitude": "25.219764"

}

],

"earthRadius": 1.0,

"response": 0.6,

"requestType": "tour"

}
```
Issue: None Found

---
## Test: Tour Around The World
willschm
### Request:
```
{

"requestType": "tour",

"earthRadius": 789,

"response": 0.7,

"places": [

{

"name": "Asahi Brewery",

"municipality": "Nagoya",

"region": "East Asia",

"country": "Japan",

"latitude": "35.226224",

"longitude": "136.957875"

},

{

"name": "Ma Che Siete Venuti A Fà",

"municipality": "Rome",

"region": "Southern Europe",

"country": "Italy",

"latitude": "41.891751",

"longitude": "12.469169"

},

{

"name": "The River Brewing Company",

"municipality": "Victoria Falls",

"region": "Southern Africa",

"country": "Zimbabwe",

"latitude": "-17.925280",

"longitude": "25.840280"

},

{

"name": "Zero40 Brewing",

"municipality": "Hyderabad",

"region": "South Asia",

"country": "India",

"latitude": "17.435660",

"longitude": "78.411740"

},

{

"name": "Tommy’s Brewing Company",

"municipality": "Trincity",

"region": "Caribbean",

"country": "Trinidad and Tobago",

"latitude": "10.634360",

"longitude": "-61.357300"

},

{

"name": "Mikkeller Taipei",

"municipality": "Taipei City",

"region": "East Asia",

"country": "Taiwan",

"latitude": "25.053684",

"longitude": "121.510158"

},

{

"name": "AbdulAhmad Annabi Brewery",

"municipality": "Kabul",

"region": "Central Asia",

"country": "Afghanistan",

"latitude": "34.9632",

"longitude": "68.8108"

},

{

"name": "Knucklehead Craft Brewing Company",

"municipality": "Webster",

"region": "North America",

"country": "United States",

"latitude": "43.206033",

"longitude": "-77.512215"

}

]

}
```
### T45 Response:
```
{

"places": [

{

"name": "Asahi Brewery",

"municipality": "Nagoya",

"region": "East Asia",

"country": "Japan",

"latitude": "35.226224",

"longitude": "136.957875"

},

{

"name": "Mikkeller Taipei",

"municipality": "Taipei City",

"region": "East Asia",

"country": "Taiwan",

"latitude": "25.053684",

"longitude": "121.510158"

},

{

"name": "Zero40 Brewing",

"municipality": "Hyderabad",

"region": "South Asia",

"country": "India",

"latitude": "17.435660",

"longitude": "78.411740"

},

{

"name": "AbdulAhmad Annabi Brewery",

"municipality": "Kabul",

"region": "Central Asia",

"country": "Afghanistan",

"latitude": "34.9632",

"longitude": "68.8108"

},

{

"name": "Ma Che Siete Venuti A Fà",

"municipality": "Rome",

"region": "Southern Europe",

"country": "Italy",

"latitude": "41.891751",

"longitude": "12.469169"

},

{

"name": "The River Brewing Company",

"municipality": "Victoria Falls",

"region": "Southern Africa",

"country": "Zimbabwe",

"latitude": "-17.925280",

"longitude": "25.840280"

},

{

"name": "Tommy’s Brewing Company",

"municipality": "Trincity",

"region": "Caribbean",

"country": "Trinidad and Tobago",

"latitude": "10.634360",

"longitude": "-61.357300"

},

{

"name": "Knucklehead Craft Brewing Company",

"municipality": "Webster",

"region": "North America",

"country": "United States",

"latitude": "43.206033",

"longitude": "-77.512215"

}

],

"earthRadius": 789.0,

"response": 0.7,

"requestType": "tour"

}
```
Issue: None Found
### T13 Response:
```
{

"places": [

{

"country": "Japan",

"latitude": "35.226224",

"name": "Asahi Brewery",

"municipality": "Nagoya",

"region": "East Asia",

"longitude": "136.957875"

},

{

"country": "Taiwan",

"latitude": "25.053684",

"name": "Mikkeller Taipei",

"municipality": "Taipei City",

"region": "East Asia",

"longitude": "121.510158"

},

{

"country": "India",

"latitude": "17.435660",

"name": "Zero40 Brewing",

"municipality": "Hyderabad",

"region": "South Asia",

"longitude": "78.411740"

},

{

"country": "Afghanistan",

"latitude": "34.9632",

"name": "AbdulAhmad Annabi Brewery",

"municipality": "Kabul",

"region": "Central Asia",

"longitude": "68.8108"

},

{

"country": "Italy",

"latitude": "41.891751",

"name": "Ma Che Siete Venuti A Fà",

"municipality": "Rome",

"region": "Southern Europe",

"longitude": "12.469169"

},

{

"country": "Zimbabwe",

"latitude": "-17.925280",

"name": "The River Brewing Company",

"municipality": "Victoria Falls",

"region": "Southern Africa",

"longitude": "25.840280"

},

{

"country": "Trinidad and Tobago",

"latitude": "10.634360",

"name": "Tommy’s Brewing Company",

"municipality": "Trincity",

"region": "Caribbean",

"longitude": "-61.357300"

},

{

"country": "United States",

"latitude": "43.206033",

"name": "Knucklehead Craft Brewing Company",

"municipality": "Webster",

"region": "North America",

"longitude": "-77.512215"

}

],

"earthRadius": 789.0,

"formula": "",

"response": 0.7,

"requestType": "tour"

}
```
Issue: Place object elements are not in the correct order.
### T14 Response:
```
{

"places": [

{

"name": "Asahi Brewery",

"municipality": "Nagoya",

"region": "East Asia",

"country": "Japan",

"latitude": "35.226224",

"longitude": "136.957875"

},

{

"name": "Mikkeller Taipei",

"municipality": "Taipei City",

"region": "East Asia",

"country": "Taiwan",

"latitude": "25.053684",

"longitude": "121.510158"

},

{

"name": "Zero40 Brewing",

"municipality": "Hyderabad",

"region": "South Asia",

"country": "India",

"latitude": "17.435660",

"longitude": "78.411740"

},

{

"name": "AbdulAhmad Annabi Brewery",

"municipality": "Kabul",

"region": "Central Asia",

"country": "Afghanistan",

"latitude": "34.9632",

"longitude": "68.8108"

},

{

"name": "Ma Che Siete Venuti A Fà",

"municipality": "Rome",

"region": "Southern Europe",

"country": "Italy",

"latitude": "41.891751",

"longitude": "12.469169"

},

{

"name": "The River Brewing Company",

"municipality": "Victoria Falls",

"region": "Southern Africa",

"country": "Zimbabwe",

"latitude": "-17.925280",

"longitude": "25.840280"

},

{

"name": "Tommy’s Brewing Company",

"municipality": "Trincity",

"region": "Caribbean",

"country": "Trinidad and Tobago",

"latitude": "10.634360",

"longitude": "-61.357300"

},

{

"name": "Knucklehead Craft Brewing Company",

"municipality": "Webster",

"region": "North America",

"country": "United States",

"latitude": "43.206033",

"longitude": "-77.512215"

}

],

"earthRadius": 789.0,

"response": 0.7,

"requestType": "tour"

}
```
Issue: None Found

---
## Test: Tour Massive Radius
willschm
### Request:
```
{

"requestType": "tour",

"earthRadius": 1000000000000000000,

"response": 0.5,

"places": [

{

"name": "Sunset Brewery",

"municipality": "San Francisco",

"region": "California",

"country": "USA",

"latitude": "37.774929",

"longitude": "-122.419418"

},

{

"name": "Mountain Peak Brewery",

"municipality": "Denver",

"region": "Colorado",

"country": "USA",

"latitude": "39.739236",

"longitude": "-104.990251"

},

{

"name": "Lakeside Brewery",

"municipality": "Toronto",

"region": "Ontario",

"country": "Canada",

"latitude": "43.653225",

"longitude": "-79.383186"

},

{

"name": "Tropic Wave Brewery",

"municipality": "Miami",

"region": "Florida",

"country": "USA",

"latitude": "25.761681",

"longitude": "-80.191788"

},

{

"name": "Royal Hop Brewery",

"municipality": "London",

"region": "England",

"country": "United Kingdom",

"latitude": "51.507351",

"longitude": "-0.127758"

},

{

"name": "Coastal Breeze Brewery",

"municipality": "Sydney",

"region": "New South Wales",

"country": "Australia",

"latitude": "-33.868820",

"longitude": "151.209290"

},

{

"name": "Northern Lights Brewery",

"municipality": "Reykjavik",

"region": "Capital Region",

"country": "Iceland",

"latitude": "64.146582",

"longitude": "-21.942635"

},

{

"name": "Desert Oasis Brewery",

"municipality": "Dubai",

"region": "Dubai",

"country": "United Arab Emirates",

"latitude": "25.276987",

"longitude": "55.296249"

}

]

}
```
### T45 Response:
```
{

"places": [

{

"name": "Sunset Brewery",

"municipality": "San Francisco",

"region": "California",

"country": "USA",

"latitude": "37.774929",

"longitude": "-122.419418"

},

{

"name": "Mountain Peak Brewery",

"municipality": "Denver",

"region": "Colorado",

"country": "USA",

"latitude": "39.739236",

"longitude": "-104.990251"

},

{

"name": "Lakeside Brewery",

"municipality": "Toronto",

"region": "Ontario",

"country": "Canada",

"latitude": "43.653225",

"longitude": "-79.383186"

},

{

"name": "Tropic Wave Brewery",

"municipality": "Miami",

"region": "Florida",

"country": "USA",

"latitude": "25.761681",

"longitude": "-80.191788"

},

{

"name": "Royal Hop Brewery",

"municipality": "London",

"region": "England",

"country": "United Kingdom",

"latitude": "51.507351",

"longitude": "-0.127758"

},

{

"name": "Coastal Breeze Brewery",

"municipality": "Sydney",

"region": "New South Wales",

"country": "Australia",

"latitude": "-33.868820",

"longitude": "151.209290"

},

{

"name": "Northern Lights Brewery",

"municipality": "Reykjavik",

"region": "Capital Region",

"country": "Iceland",

"latitude": "64.146582",

"longitude": "-21.942635"

},

{

"name": "Desert Oasis Brewery",

"municipality": "Dubai",

"region": "Dubai",

"country": "United Arab Emirates",

"latitude": "25.276987",

"longitude": "55.296249"

}

],

"earthRadius": 1.0E18,

"response": 0.5,

"requestType": "tour"

}
```
Issue: None Found
### T13 Response:
```
{

"places": [

{

"country": "USA",

"latitude": "37.774929",

"name": "Sunset Brewery",

"municipality": "San Francisco",

"region": "California",

"longitude": "-122.419418"

},

{

"country": "Australia",

"latitude": "-33.868820",

"name": "Coastal Breeze Brewery",

"municipality": "Sydney",

"region": "New South Wales",

"longitude": "151.209290"

},

{

"country": "United Arab Emirates",

"latitude": "25.276987",

"name": "Desert Oasis Brewery",

"municipality": "Dubai",

"region": "Dubai",

"longitude": "55.296249"

},

{

"country": "United Kingdom",

"latitude": "51.507351",

"name": "Royal Hop Brewery",

"municipality": "London",

"region": "England",

"longitude": "-0.127758"

},

{

"country": "Iceland",

"latitude": "64.146582",

"name": "Northern Lights Brewery",

"municipality": "Reykjavik",

"region": "Capital Region",

"longitude": "-21.942635"

},

{

"country": "Canada",

"latitude": "43.653225",

"name": "Lakeside Brewery",

"municipality": "Toronto",

"region": "Ontario",

"longitude": "-79.383186"

},

{

"country": "USA",

"latitude": "25.761681",

"name": "Tropic Wave Brewery",

"municipality": "Miami",

"region": "Florida",

"longitude": "-80.191788"

},

{

"country": "USA",

"latitude": "39.739236",

"name": "Mountain Peak Brewery",

"municipality": "Denver",

"region": "Colorado",

"longitude": "-104.990251"

}

],

"earthRadius": 1.0E18,

"formula": "",

"response": 0.5,

"requestType": "tour"

}
```
Issue: response contains a formula element when it shouldn't.
### T14 Response:
```
{

"places": [

{

"name": "Sunset Brewery",

"municipality": "San Francisco",

"region": "California",

"country": "USA",

"latitude": "37.774929",

"longitude": "-122.419418"

},

{

"name": "Mountain Peak Brewery",

"municipality": "Denver",

"region": "Colorado",

"country": "USA",

"latitude": "39.739236",

"longitude": "-104.990251"

},

{

"name": "Lakeside Brewery",

"municipality": "Toronto",

"region": "Ontario",

"country": "Canada",

"latitude": "43.653225",

"longitude": "-79.383186"

},

{

"name": "Tropic Wave Brewery",

"municipality": "Miami",

"region": "Florida",

"country": "USA",

"latitude": "25.761681",

"longitude": "-80.191788"

},

{

"name": "Northern Lights Brewery",

"municipality": "Reykjavik",

"region": "Capital Region",

"country": "Iceland",

"latitude": "64.146582",

"longitude": "-21.942635"

},

{

"name": "Royal Hop Brewery",

"municipality": "London",

"region": "England",

"country": "United Kingdom",

"latitude": "51.507351",

"longitude": "-0.127758"

},

{

"name": "Desert Oasis Brewery",

"municipality": "Dubai",

"region": "Dubai",

"country": "United Arab Emirates",

"latitude": "25.276987",

"longitude": "55.296249"

},

{

"name": "Coastal Breeze Brewery",

"municipality": "Sydney",

"region": "New South Wales",

"country": "Australia",

"latitude": "-33.868820",

"longitude": "151.209290"

}

],

"earthRadius": 1.0E18,

"response": 0.5,

"requestType": "tour"

}
```
Issue: None Found

---

## Test: Tour Response 0.0
willschm
### Request:
```
{

"requestType": "tour",

"earthRadius": 777,

"response": 0.0,

"places": [

{

"name": "Banange Brewing Company",

"municipality": "Kampala",

"country": "Uganda",

"latitude": "0.3223924",

"longitude": "32.5835994",

"altitude": "2728"

},

{

"name": "2085 Brewery",

"municipality": "Kyiv",

"country": "Ukraine",

"latitude": "50.4607",

"longitude": "30.6392",

"altitude": "343"

},

{

"name": "Cerveceria Vieja Chela",

"municipality": "Departamento de Montevideo",

"country": "Uruguay",

"latitude": "-34.89620",

"longitude": "-56.14678",

"altitude": "104"

},

{

"name": "Dushanbe Brewery",

"municipality": "Dushanbe",

"country": "Tajikistan",

"latitude": "38.57982378149015",

"longitude": "68.80152022889366",

"altitude": "2316"

},

{

"name": "Samarkand-Praga-Pivo",

"municipality": "Samarkand",

"country": "Uzbekistan",

"latitude": "39.6608957",

"longitude": "66.9476184",

"altitude": "2296"

},

{

"name": "Lousiane Brewhouse Restaurant",

"municipality": "Nha Trang",

"country": "Vietnam",

"latitude": "12.318880",

"longitude": "109.159640",

"altitude": "16"

},

{

"name": "Brasserie Wallis-et-Futuna",

"municipality": "Mata-Utu",

"country": "Wallis and Futuna Islands",

"latitude": "13.282273",

"longitude": "176.176464",

"altitude": "47"

},

{

"name": "Zambian Breweries Plc",

"municipality": "Lusaka",

"country": "Zambia",

"latitude": "-15.39278",

"longitude": "28.24750",

"altitude": "1272"

}

]

}
```
### T45 Response:
```
{

"places": [

{

"name": "Banange Brewing Company",

"municipality": "Kampala",

"country": "Uganda",

"latitude": "0.3223924",

"longitude": "32.5835994",

"altitude": "2728"

},

{

"name": "2085 Brewery",

"municipality": "Kyiv",

"country": "Ukraine",

"latitude": "50.4607",

"longitude": "30.6392",

"altitude": "343"

},

{

"name": "Cerveceria Vieja Chela",

"municipality": "Departamento de Montevideo",

"country": "Uruguay",

"latitude": "-34.89620",

"longitude": "-56.14678",

"altitude": "104"

},

{

"name": "Dushanbe Brewery",

"municipality": "Dushanbe",

"country": "Tajikistan",

"latitude": "38.57982378149015",

"longitude": "68.80152022889366",

"altitude": "2316"

},

{

"name": "Samarkand-Praga-Pivo",

"municipality": "Samarkand",

"country": "Uzbekistan",

"latitude": "39.6608957",

"longitude": "66.9476184",

"altitude": "2296"

},

{

"name": "Lousiane Brewhouse Restaurant",

"municipality": "Nha Trang",

"country": "Vietnam",

"latitude": "12.318880",

"longitude": "109.159640",

"altitude": "16"

},

{

"name": "Brasserie Wallis-et-Futuna",

"municipality": "Mata-Utu",

"country": "Wallis and Futuna Islands",

"latitude": "13.282273",

"longitude": "176.176464",

"altitude": "47"

},

{

"name": "Zambian Breweries Plc",

"municipality": "Lusaka",

"country": "Zambia",

"latitude": "-15.39278",

"longitude": "28.24750",

"altitude": "1272"

}

],

"earthRadius": 777.0,

"response": 0.0,

"requestType": "tour"

}
```
Issue: None Found
### T13 Response:
```
{

"places": [

{

"country": "Uganda",

"altitude": "2728",

"latitude": "0.3223924",

"name": "Banange Brewing Company",

"municipality": "Kampala",

"longitude": "32.5835994"

},

{

"country": "Ukraine",

"altitude": "343",

"latitude": "50.4607",

"name": "2085 Brewery",

"municipality": "Kyiv",

"longitude": "30.6392"

},

{

"country": "Uruguay",

"altitude": "104",

"latitude": "-34.89620",

"name": "Cerveceria Vieja Chela",

"municipality": "Departamento de Montevideo",

"longitude": "-56.14678"

},

{

"country": "Tajikistan",

"altitude": "2316",

"latitude": "38.57982378149015",

"name": "Dushanbe Brewery",

"municipality": "Dushanbe",

"longitude": "68.80152022889366"

},

{

"country": "Uzbekistan",

"altitude": "2296",

"latitude": "39.6608957",

"name": "Samarkand-Praga-Pivo",

"municipality": "Samarkand",

"longitude": "66.9476184"

},

{

"country": "Vietnam",

"altitude": "16",

"latitude": "12.318880",

"name": "Lousiane Brewhouse Restaurant",

"municipality": "Nha Trang",

"longitude": "109.159640"

},

{

"country": "Wallis and Futuna Islands",

"altitude": "47",

"latitude": "13.282273",

"name": "Brasserie Wallis-et-Futuna",

"municipality": "Mata-Utu",

"longitude": "176.176464"

},

{

"country": "Zambia",

"altitude": "1272",

"latitude": "-15.39278",

"name": "Zambian Breweries Plc",

"municipality": "Lusaka",

"longitude": "28.24750"

}

],

"earthRadius": 777.0,

"formula": "",

"response": 0.0,

"requestType": "tour"

}
```
Issue: None Found
### T14 Response:
```
{

"places": [

{

"name": "Banange Brewing Company",

"municipality": "Kampala",

"country": "Uganda",

"latitude": "0.3223924",

"longitude": "32.5835994",

"altitude": "2728"

},

{

"name": "2085 Brewery",

"municipality": "Kyiv",

"country": "Ukraine",

"latitude": "50.4607",

"longitude": "30.6392",

"altitude": "343"

},

{

"name": "Cerveceria Vieja Chela",

"municipality": "Departamento de Montevideo",

"country": "Uruguay",

"latitude": "-34.89620",

"longitude": "-56.14678",

"altitude": "104"

},

{

"name": "Dushanbe Brewery",

"municipality": "Dushanbe",

"country": "Tajikistan",

"latitude": "38.57982378149015",

"longitude": "68.80152022889366",

"altitude": "2316"

},

{

"name": "Samarkand-Praga-Pivo",

"municipality": "Samarkand",

"country": "Uzbekistan",

"latitude": "39.6608957",

"longitude": "66.9476184",

"altitude": "2296"

},

{

"name": "Lousiane Brewhouse Restaurant",

"municipality": "Nha Trang",

"country": "Vietnam",

"latitude": "12.318880",

"longitude": "109.159640",

"altitude": "16"

},

{

"name": "Brasserie Wallis-et-Futuna",

"municipality": "Mata-Utu",

"country": "Wallis and Futuna Islands",

"latitude": "13.282273",

"longitude": "176.176464",

"altitude": "47"

},

{

"name": "Zambian Breweries Plc",

"municipality": "Lusaka",

"country": "Zambia",

"latitude": "-15.39278",

"longitude": "28.24750",

"altitude": "1272"

}

],

"earthRadius": 777.0,

"response": 0.0,

"requestType": "tour"

}
```
Issue: None Found

---
## Test: Tour Null Island
willschm
### Request:
```
{

"requestType": "tour",

"earthRadius": 16,

"response": 0.01,

"places": [

{

"name": "Null Island",

"municipality": "Atlantic Ocean",

"region": "Southern Atlantic",

"country": "International Waters",

"latitude": "0.0",

"longitude": "0.0"

},

{

"name": "AXA Brewing Company",

"municipality": "Sandy Ground",

"country": "Anguilla",

"latitude": "18.1210",

"longitude": "-63.0453"

},

{

"name": "2SIX8 Craft Brewery",

"municipality": "English Harbour Town",

"country": "Antigua and Barbuda",

"latitude": "17.022739",

"longitude": "-61.770096"

},

{

"name": "Buller Brewing Company",

"municipality": "Buenos Aires",

"country": "Argentina",

"latitude": "-34.3519",

"longitude": "-58.2332"

},

{

"name": "Sevan Brewery",

"municipality": "Sevan",

"country": "Armenia",

"latitude": "40.53683",

"longitude": "44.94100"

},

{

"name": "Chubato Beer World",

"municipality": "Oranjestad",

"country": "Aruba",

"latitude": "12.550723",

"longitude": "-70.579269"

},

{

"name": "Drunken Drone Brewery",

"municipality": "Kingscote",

"country": "Australia",

"latitude": "-35.832518",

"longitude": "137.564555"

},

{

"name": "The Beer of Barbados",

"municipality": "Saint Michael",

"country": "Barbados",

"latitude": "13.1",

"longitude": "-59.61667"

}

]

}
```
### T45 Response:
```
{

"places": [

{

"name": "Null Island",

"municipality": "Atlantic Ocean",

"region": "Southern Atlantic",

"country": "International Waters",

"latitude": "0.0",

"longitude": "0.0"

},

{

"name": "AXA Brewing Company",

"municipality": "Sandy Ground",

"country": "Anguilla",

"latitude": "18.1210",

"longitude": "-63.0453"

},

{

"name": "2SIX8 Craft Brewery",

"municipality": "English Harbour Town",

"country": "Antigua and Barbuda",

"latitude": "17.022739",

"longitude": "-61.770096"

},

{

"name": "Buller Brewing Company",

"municipality": "Buenos Aires",

"country": "Argentina",

"latitude": "-34.3519",

"longitude": "-58.2332"

},

{

"name": "Sevan Brewery",

"municipality": "Sevan",

"country": "Armenia",

"latitude": "40.53683",

"longitude": "44.94100"

},

{

"name": "Chubato Beer World",

"municipality": "Oranjestad",

"country": "Aruba",

"latitude": "12.550723",

"longitude": "-70.579269"

},

{

"name": "Drunken Drone Brewery",

"municipality": "Kingscote",

"country": "Australia",

"latitude": "-35.832518",

"longitude": "137.564555"

},

{

"name": "The Beer of Barbados",

"municipality": "Saint Michael",

"country": "Barbados",

"latitude": "13.1",

"longitude": "-59.61667"

}

],

"earthRadius": 16.0,

"response": 0.01,

"requestType": "tour"

}
```
Issue: None Found
### T13 Response:
```
{

"places": [

{

"country": "International Waters",

"latitude": "0.0",

"name": "Null Island",

"municipality": "Atlantic Ocean",

"region": "Southern Atlantic",

"longitude": "0.0"

},

{

"country": "Barbados",

"latitude": "13.1",

"name": "The Beer of Barbados",

"municipality": "Saint Michael",

"longitude": "-59.61667"

},

{

"country": "Antigua and Barbuda",

"latitude": "17.022739",

"name": "2SIX8 Craft Brewery",

"municipality": "English Harbour Town",

"longitude": "-61.770096"

},

{

"country": "Anguilla",

"latitude": "18.1210",

"name": "AXA Brewing Company",

"municipality": "Sandy Ground",

"longitude": "-63.0453"

},

{

"country": "Aruba",

"latitude": "12.550723",

"name": "Chubato Beer World",

"municipality": "Oranjestad",

"longitude": "-70.579269"

},

{

"country": "Argentina",

"latitude": "-34.3519",

"name": "Buller Brewing Company",

"municipality": "Buenos Aires",

"longitude": "-58.2332"

},

{

"country": "Australia",

"latitude": "-35.832518",

"name": "Drunken Drone Brewery",

"municipality": "Kingscote",

"longitude": "137.564555"

},

{

"country": "Armenia",

"latitude": "40.53683",

"name": "Sevan Brewery",

"municipality": "Sevan",

"longitude": "44.94100"

}

],

"earthRadius": 16.0,

"formula": "",

"response": 0.01,

"requestType": "tour"

}
```
Issue: None Found
### T14 Response:
```
{

"places": [

{

"name": "Null Island",

"municipality": "Atlantic Ocean",

"region": "Southern Atlantic",

"country": "International Waters",

"latitude": "0.0",

"longitude": "0.0"

},

{

"name": "Sevan Brewery",

"municipality": "Sevan",

"country": "Armenia",

"latitude": "40.53683",

"longitude": "44.94100"

},

{

"name": "AXA Brewing Company",

"municipality": "Sandy Ground",

"country": "Anguilla",

"latitude": "18.1210",

"longitude": "-63.0453"

},

{

"name": "2SIX8 Craft Brewery",

"municipality": "English Harbour Town",

"country": "Antigua and Barbuda",

"latitude": "17.022739",

"longitude": "-61.770096"

},

{

"name": "The Beer of Barbados",

"municipality": "Saint Michael",

"country": "Barbados",

"latitude": "13.1",

"longitude": "-59.61667"

},

{

"name": "Chubato Beer World",

"municipality": "Oranjestad",

"country": "Aruba",

"latitude": "12.550723",

"longitude": "-70.579269"

},

{

"name": "Buller Brewing Company",

"municipality": "Buenos Aires",

"country": "Argentina",

"latitude": "-34.3519",

"longitude": "-58.2332"

},

{

"name": "Drunken Drone Brewery",

"municipality": "Kingscote",

"country": "Australia",

"latitude": "-35.832518",

"longitude": "137.564555"

}

],

"earthRadius": 16.0,

"response": 0.01,

"requestType": "tour"

}
```
Issue: None Found