## Test: Same Location
willschm
### Request:
```
{
    "requestType": "distances",
    "places": [
        {
            "name": "Fort Collins, Colorado",
            "latitude": "40.5853",
            "longitude": "-105.0844"
        },
        {
            "name": "Fort Collins, Colorado",
            "latitude": "40.5853",
            "longitude": "-105.0844"
        }
    ],
    "earthRadius": 637800000
}

```
### T45 Response:
```
{
    "places": [
        {
            "name": "Fort Collins, Colorado",
            "latitude": "40.5853",
            "longitude": "-105.0844"
        },
        {
            "name": "Fort Collins, Colorado",
            "latitude": "40.5853",
            "longitude": "-105.0844"
        }
    ],
    "distances": [
        0,
        0
    ],
    "earthRadius": 6.378E8,
    "requestType": "distances"
}
```
Issue: None found
### T13 Reponse:
```
{
    "places": [
        {
            "latitude": "40.5853",
            "name": "Fort Collins, Colorado",
            "longitude": "-105.0844"
        },
        {
            "latitude": "40.5853",
            "name": "Fort Collins, Colorado",
            "longitude": "-105.0844"
        }
    ],
    "earthRadius": 6.378E8,
    "formula": "",
    "distances": [
        0,
        0
    ],
    "requestType": "distances"
}
```
Issue: None found
### T14 Response:
```
{
    "places": [
        {
            "name": "Fort Collins, Colorado",
            "latitude": "40.5853",
            "longitude": "-105.0844"
        },
        {
            "name": "Fort Collins, Colorado",
            "latitude": "40.5853",
            "longitude": "-105.0844"
        }
    ],
    "earthRadius": 6.378E8,
    "distances": [
        0,
        0
    ],
    "requestType": "distances"
}
```
Issue: None Found

---
## Test: Massive Radius
willschm
### Request:
```
{

"requestType" : "distances",

"places" :[{"name": "Colorado, United States of America", "latitude": "40.302135", "longitude": "-105.084508"},

{"name": "Telangana, India", "latitude": "17.516733", "longitude": "78.477900"},

{"name": "Sydney, Australia", "latitude": "-33.857387", "longitude": "151.202419"},

{"name": "Chubut Province, Argentina", "latitude": "-43.781303", "longitude": "-66.574488"}

],

"earthRadius" : 1000000000000000000

}
```
### T45 Response:
```
{

"places": [

{

"name": "Colorado, United States of America",

"latitude": "40.302135",

"longitude": "-105.084508"

},

{

"name": "Telangana, India",

"latitude": "17.516733",

"longitude": "78.477900"

},

{

"name": "Sydney, Australia",

"latitude": "-33.857387",

"longitude": "151.202419"

},

{

"name": "Chubut Province, Argentina",

"latitude": "-43.781303",

"longitude": "-66.574488"

}

],

"distances": [

2130803497818100224,

1503258380192108544,

1659321789383798272,

1587476957848462336

],

"earthRadius": 1.0E18,

"requestType": "distances"

}
```
Issue: None Found
### T13 Response:
```
{

"places": [

{

"latitude": "40.302135",

"name": "Colorado, United States of America",

"longitude": "-105.084508"

},

{

"latitude": "17.516733",

"name": "Telangana, India",

"longitude": "78.477900"

},

{

"latitude": "-33.857387",

"name": "Sydney, Australia",

"longitude": "151.202419"

},

{

"latitude": "-43.781303",

"name": "Chubut Province, Argentina",

"longitude": "-66.574488"

}

],

"earthRadius": 1.0E18,

"formula": "",

"distances": [

2130803497818100224,

1503258380192108544,

1659321789383798272,

1587476957848462336

],

"requestType": "distances"

}
```
Issue: None Found
### T14 Response:
```
{

"places": [

{

"name": "Colorado, United States of America",

"latitude": "40.302135",

"longitude": "-105.084508"

},

{

"name": "Telangana, India",

"latitude": "17.516733",

"longitude": "78.477900"

},

{

"name": "Sydney, Australia",

"latitude": "-33.857387",

"longitude": "151.202419"

},

{

"name": "Chubut Province, Argentina",

"latitude": "-43.781303",

"longitude": "-66.574488"

}

],

"earthRadius": 1.0E18,

"distances": [

2130803497818100224,

1503258380192108544,

1659321789383798272,

1587476957848462336

],

"requestType": "distances"

}
```
Issue: None Found

---
## Test: Four Distant Locations
willschm
### Request:
```
{

"requestType": "distances",

"places": [

{"name":"Los Angeles", "latitude": "34.1", "longitude": "-118.2"},

{"name": "Seoul", "latitude": "37.5", "longitude": "127.0"},

{"name": "Rio de Janeiro", "latitude": "-22.9", "longitude": "-43.2"},

{"name": "Sydney", "latitude": "-33.9", "longitude": "151.2"}

],

"earthRadius": 3858916.4

}
```
### T45 Response:
```
{

"places": [

{

"name": "Los Angeles",

"latitude": "34.1",

"longitude": "-118.2"

},

{

"name": "Seoul",

"latitude": "37.5",

"longitude": "127.0"

},

{

"name": "Rio de Janeiro",

"latitude": "-22.9",

"longitude": "-43.2"

},

{

"name": "Sydney",

"latitude": "-33.9",

"longitude": "151.2"

}

],

"distances": [

5807709,

10987989,

8187846,

7318090

],

"earthRadius": 3858916.4,

"requestType": "distances"

}
```
Issue: None Found
### T13 Response:
```
{

"places": [

{

"latitude": "34.1",

"name": "Los Angeles",

"longitude": "-118.2"

},

{

"latitude": "37.5",

"name": "Seoul",

"longitude": "127.0"

},

{

"latitude": "-22.9",

"name": "Rio de Janeiro",

"longitude": "-43.2"

},

{

"latitude": "-33.9",

"name": "Sydney",

"longitude": "151.2"

}

],

"earthRadius": 3858916.4,

"formula": "",

"distances": [

5807709,

10987989,

8187846,

7318090

],

"requestType": "distances"

}
```
Issue: None Found
### T14 Response:
```
{

"places": [

{

"name": "Los Angeles",

"latitude": "34.1",

"longitude": "-118.2"

},

{

"name": "Seoul",

"latitude": "37.5",

"longitude": "127.0"

},

{

"name": "Rio de Janeiro",

"latitude": "-22.9",

"longitude": "-43.2"

},

{

"name": "Sydney",

"latitude": "-33.9",

"longitude": "151.2"

}

],

"earthRadius": 3858916.4,

"distances": [

5807709,

10987989,

8187846,

7318090

],

"requestType": "distances"

}
```
Issue: None Found

---
## Test: Mountains
willschm
### Request:
```
{

"requestType": "distances",

"places": [

{"name": "Mount Whitney", "latitude": "36.5785", "longitude": "118.2923"},

{"name": "Mount Elbrus", "latitude": "43.3499", "longitude": "42.4453"},

{"name": "Mount Everest", "latitude": "27.9881", "longitude": "86.9249"},

{"name": "Mount Kilimanjaro", "latitude": "-3.0673", "longitude": "37.3556"}

],

"earthRadius": 3796510

}
```
### T45 Response:
```
{

"places": [

{

"name": "Mount Whitney",

"latitude": "36.5785",

"longitude": "118.2923"

},

{

"name": "Mount Elbrus",

"latitude": "43.3499",

"longitude": "42.4453"

},

{

"name": "Mount Everest",

"latitude": "27.9881",

"longitude": "86.9249"

},

{

"name": "Mount Kilimanjaro",

"latitude": "-3.0673",

"longitude": "37.3556"

}

],

"distances": [

3744149,

2565101,

3767357,

5604501

],

"earthRadius": 3796510.0,

"requestType": "distances"

}
```
Issue: None Found
### T13 Response:
```
{

"places": [

{

"latitude": "36.5785",

"name": "Mount Whitney",

"longitude": "118.2923"

},

{

"latitude": "43.3499",

"name": "Mount Elbrus",

"longitude": "42.4453"

},

{

"latitude": "27.9881",

"name": "Mount Everest",

"longitude": "86.9249"

},

{

"latitude": "-3.0673",

"name": "Mount Kilimanjaro",

"longitude": "37.3556"

}

],

"earthRadius": 3796510.0,

"formula": "",

"distances": [

3744149,

2565101,

3767357,

5604501

],

"requestType": "distances"

}
```
Issue: None Found
### T14 Response:
```
{

"places": [

{

"name": "Mount Whitney",

"latitude": "36.5785",

"longitude": "118.2923"

},

{

"name": "Mount Elbrus",

"latitude": "43.3499",

"longitude": "42.4453"

},

{

"name": "Mount Everest",

"latitude": "27.9881",

"longitude": "86.9249"

},

{

"name": "Mount Kilimanjaro",

"latitude": "-3.0673",

"longitude": "37.3556"

}

],

"earthRadius": 3796510.0,

"distances": [

3744149,

2565101,

3767357,

5604501

],

"requestType": "distances"

}
```
Issue: None Found

---
## Test: Radius Less Than One
### Request:
```
{

"requestType": "distances",

"places": [

{

"name": "Shibuya",

"latitude": "35.660215",

"longitude": "139.705934"

},

{

"name": "Pratt Institute",

"latitude": "40.691434",

"longitude": "-73.962974"

},

{

"name": "Lake Grace",

"latitude": "-33.097371",

"longitude": "118.472768"

},

{

"name": "Cuevas",

"latitude": "-27.042616",

"longitude": "-66.638780"

}

],

"earthRadius": 0.1

}
```
### T45 Response:
```
400
```
Issue: There is no response when radius is less than 1.0.
### T13 Response:
```
400
```
Issue: There is no response when radius is less than 1.0.
### T14 Response:
```
400
```
Issue: There is no response when radius is less than 1.0.