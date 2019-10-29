# FOSS4G Oceania 2019 Workshops

## QGIS Processing Models and the Graphical Modeller

***
Requires: https://github.com/pgssimon/qgis_pick_a_point

***


The graphical modeller is a powerful component that we can use to define a workflow and run a chain of algorithms (a processing model).

A normal session with the processing framework tools includes more than running a single algorithm. Usually several of them are run to obtain a result, and the outputs of some of those algorithms are used as input for some of the other ones.

Using the graphical modeller, that workflow can be put into a processing model, which will run all the necessary algorithms in a single run, thus simplifying the whole process and automating it.


In this workshop we will create a processing model in the graphical modeller that displays buildings affected by some event within a distance from an event location.  

The affected buildings are determined by 
* Clicking a point on the map canvas to define an event location,
* travelling a distance along the road network from the event location, 
* buffering the travel distance to intersect land parcels, 
* extracting building footprints that that intersect the land parcels.


[Start here...](../master/QGIS-Processing-Models-and-the-Graphical-Modeller.md)
