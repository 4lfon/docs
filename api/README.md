
# REST API

## /nearest 

Returns the nearest bus stops and bike stations ("jump points" in general) from 
a location.

- URL: /nearest
- HTTP method: POST

### Input parameters

```
{
    latitude: 43.3697232,
    longitude: -8.4203841,
    precision: 40.3
}
```

- latitude (float): North-south position of a point on the Earth's surface.
- longitude (float): East-west position of a point on the Earth's surface.
- precision (float): Maximum radio error in meters.


### Response

Returns the nearest 10 jump points ordered by distance from the input location.

```
{
    jumps: [
    	{ 
            id: 76,
    	    latitude: 43.3674647,
            longitude: -8.438327,
            distance: 290,
            mean: "bus",
            info: {
                address: "Ronda de Outeiro, 54"
            }
	},
    	{ 
            id: 34,
    	    latitude: 43.3848483,
            longitude: -8.433362,
            distance: 434,
            mean: "bike",
            info: {
                address: "Estación de trenes"
            }
	},
    	{ 
            id: 77,
    	    latitude: 43.383848,
            longitude: -8.433838,
            distance: 560,
            mean: "bus",
            info: {
                address: "Alfonso Molina, 112"
            }
	}

        ...
    ]
}
```

- jumps (array): Ordered list with the 10 nearest jumps.
    - id (integer): unique identifier for the jump.
    - latitude (float): location component of the jump.
    - longitude (float): location component ot the jump.
    - distance (float) : distance in meters to the jump.
    - mean (string): mean of transport (currently "bus" or "bike").
    - info (object): extra info about the jump.
       - address (string): human understable location.


