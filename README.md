# FOSS4G Oceania 2019 Workshops

## QGIS Processing Models and the Graphical Modeller
[QGIS Processing Models and the Graphical Modeller](../blob/master/QGIS-Processing-Models-and-the-Graphical-Modeller.md)

The graphical modeller is a powerful component that we can use to define a workflow and run a chain of algorithms (a processing model).

A normal session with the processing framework tools includes more than running a single algorithm. Usually several of them are run to obtain a result, and the outputs of some of those algorithms are used as input for some of the other ones.

Using the graphical modeller, that workflow can be put into a processing model, which will run all the necessary algorithms in a single run, thus simplifying the whole process and automating it.


In this workshop we will create a processing model in the graphical modeller that displays buildings affected by some event within a distance from an event location.  

The affected buildings are determined by 
* Clicking a point on the map canvas to define an event location,
* travelling a distance along the road network from the event location, 
* buffering the travel distance to intersect land parcels, 
* extracting building footprints that that intersect the land parcels.

The Inputs
* Event location point chosen on the Map Canvas
* Road network layer
* Travel distance value
* Travel distance buffer value
* Land parcel layer
* Building footprints layer

The outputs
* Event location point layer
* Affected road network line layer
* Travel distance buffer polygon layer
* Affected buildings polygon layer
