# leaflet-latlng-point

## Description
Objects to create and manage a doubly-linked List of points representing a polyline or polygon

- `L.LatLngPointList`     = A doubly-linked List of points representing a polyline or polygon
- `L.LatLngPoint`         = A point in L.LatLngPointList
- `L.LatLngDistancePoint` = Extension of LatLngPoint representing a point on the polyline given by the distance from the start

## Installation
### bower
`bower install https://github.com/FCOO/leaflet-latlng-point.git --save`

## Demo
http://FCOO.github.io/leaflet-latlng-point/demo/ 

## L.LatLngPointList
	var myLatLngPointList = new L.LatLngPointList(options );
	options = {
		isPolygon       : false,
        isRhumb         : false,
        pointConstructor: L.latLngPoint, //Constructor for the points in the list
    	list            : []			 //[] of L.LatLng
	}

### Methods
    .getDistance();             //Return the total distance [m]
	.update();
	.append( latLng, options ); //Add a point to the end of the list
	.insert( latLng, index );   //Insert a point after the point at list[index]
	.remove( index );           //Remove the latLngPoint at index

## `L.LatLngPoint`

Get created automatic when a point is added to the list a la `myLatLngPointList.append([55, 12])`
Its properties gets updated automatic

### Properties
	L.LatLngPoint
		.prevPoint //The previous LatLngPoint
        .nextPoint //The next LatLngPoint
        .totalDistance		//Distance from the start
		.totalRhumbDistance //Rhumb-distance from the start
		.prev = { //Properties of the section from prevPoint to this
        	.distance
            .bearing
            .finalBearing
			.rhumbDistance
			.rhumbBearing 
        }
		.next = { //Properties of the section from this to nextPoint
			.distance
            .bearing
            .finalBearing
            .rhumbDistance
            .rhumbBearing
		}

## `L.LatLngDistancePoint`
Extension of LatLngPoint representing a point on the polyline given by the distance from the start
	
### Methods
    .setDistance(  distance ); //Set the distance from the start of the line and updates the properties


## Copyright and License
This plugin is licensed under the [MIT license](https://github.com/FCOO/leaflet-latlng-point/LICENSE).

Copyright (c) 2018 [FCOO](https://github.com/FCOO)

## Contact information

Niels Holt nho@fcoo.dk
