Processing Models
=================

The objectives of this module are to learn about:

-   Processing Models

-   The Graphical Modeller

Processing Models and the Graphical Modeler
-------------------------------------------

The graphical modeler, is a powerful component that we can use to define a
workflow and run a chain of algorithms (a processing model).

A normal session with the processing framework tools includes more than running
a single algorithm. Usually several of them are run to obtain a result, and the
outputs of some of those algorithms are used as input for some of the other
ones.

Using the graphical modeler, that workflow can be put into a processing model,
which will run all the necessary algorithms in a single run, thus simplifying
the whole process and automating it.

![](media/e03bdfc55353bf6a3a6f2b154872d41a.png)

Exercise – Affected Buildings Model
-----------------------------------

In this exercise we will create a processing model in the graphical modeler that
displays buildings affected by some event within a distance from the event
location.

The affected buildings are determined by

-   travelling a distance along the road network from the event location,

-   buffering the travel distance to intersect land parcels,

-   extracting building footprints that that intersect the land parcels.

![](media/4bc9d0c0a43c32e9dfc60274015e0d19.png)

![](media/eb212388ab94061ec861e2bc2b3b6c9f.png)

The Inputs

-   Event location point chosen on the Map Canvas

-   Road network layer

-   Travel distance value

-   Travel distance buffer value

-   Land parcel layer

-   Building footprints layer

The outputs

-   Event location point layer

-   Affected road network line layer

-   Travel distance buffer polygon layer

-   Affected buildings polygon layer

### Creating the model

-   In the **Processing toolbox**, click the

    ![](media/9a0371869e3f6aa89199baab2971246d.png)

    **Models** tool, choose **Create New Model…**  
      
    

    ![](media/e23eed7160b50688df0062bf897ee4d4.png)

      
      
    Note that the graphical **Processing modeler** window opens  
      
    

    ![](media/e737fd71b0b9c59f9d24f2de7bbae2c0.png)

-   In the **Model properties** panel, set the **Name** to **Affected
    Buildings**

-   In the **Model properties** panel, set the **Group** to **Training**  
      
    

    ![](media/7467f8a23c0a95e8a7c15e8aad014438.png)

-   Save the model by clicking the save tool on the toolbar  
      
    The **Save Model** dialog will be displayed.

-   Set the **File name** to **affectedbuildings**  
      
    

    ![](media/fd2759dd0af0c172cdf77ec8a2d72257.png)

The save path for your model will be like…

**C:\\Users\\training\\AppData\\Roaming\\QGIS\\QGIS3\\profiles\\default\\processing\\models**  


-   Click the **Save** button

### Adding the first input parameter

Our first input is the Event location point that will be chosen on the Map
Canvas

-   In the **Inputs** panel, double click the **Point** input  
      
    Note that a **Parameter Definition** dialog opens

-   Set **Parameter name** to **Event Location**  
      
    

    ![](media/13ca9ea98596aa5728ef0bb11a2acdc0.png)

-   Click the **OK** button  
      
    Note that we now have the first input parameter in our graphical modeler…  
      
    

    ![](media/2c28559aef17d7dd69ff3ccc736d2cb5.png)

      
    The input parameter can be dragged in the window and to edit double click.

### Adding the first algorithm and output

Our next task is to assign this **input** parameter to an **algorithm**

-   Switch to the **Algorithms** panel (use the tabs at the bottom of the Inputs
    panel)  
      
    Note that the panel now displays the different categories of algorithms
    available to the graphical modeler…  
      
    

    ![](media/e675c311e6852f16cdeaf85957af2570.png)

-   **Expand** the **Scripts** category, then expand **Custom Scripts**

-   **Double click** the **Pick point on map** script  
      
    Note that a dialog opens for the **Pick point on map** script…  
      
    

    ![](media/118c1bb23e0eb72e563a8c96bba96987.png)

-   Set **Pick a point on the map (x, y)** dropdown list to **Event Location**
    (that’s the input parameter we defined previously)  
      
    

    ![](media/df847f80517ab0c0ddd1efdbd498c01e.png)

-   Set **Output layer** to **Event location** (this will be the name of the
    output layer displaying the event location point in QGIS)  
      
    

    ![](media/8553d79aba5c22f60f11c946757704eb.png)

-   Click the **OK** button  
      
    Note that the **Pick point on map** script has been added to the graphical
    modeler, along with the output layer…  
      
    

    ![](media/fe4592c64de0056b737c539c31df6f9a.png)

-   Re-position the items to look like below…  
      
    

    ![](media/b55cf220384a83fb45f006419fb128e1.png)

-   Save the model by clicking the save tool on the toolbar

### Testing the model

We now have an input parameter, an algorithm and an output – let’s test the
model.

-   Close the **Processing Modeler** window

-   In the **Processing toolbox**, expand the **Models** category, then expand
    the **Training** group  
      
    

    ![](media/997aeb612ecc2dcf4bf0993ede7cc33c.png)

-   **Double click** the model named **Affected Buildings**  
      
    Note that Affected Buildings dialog is displayed…  
      
    

    ![](media/40a1c535e3450a10e8801266e1e3efc2.png)

-   Click the option button next to the **Event location (x, y)** textbox  
      
    Note that we are switched to the **Map Canvas** and we can click a location
    for the event on the Map Canvas.  
      
    **Click a location** as indicated below on the **Map Canvas**…  
      
    

    ![](media/6aec8dddaf1f0a6feb8fba78475821d2.png)

-   The **Event location (x, y)** textbox will now be populated with the
    coordinates of the location we clicked on the Map Canvas  
      
    

    ![](media/44a02839763d02c4f1528b77b691adfc.png)

-   Leave the **Event location** output set to **[Create temporary layer]**  
      
    

    ![](media/655ddcd8b2365d54f7b8f373bbe774eb.png)

-   Click the **Run** button

-   When the **Coordinate Reference System Selector** dialog opens, click the
    **OK** button  
      
    

    ![](media/802db11a77491e9bca2f8c5c3d2536bd.png)

-   In the **Affected Buildings** dialog, click the **Close** button

The **Map Canvas** should now show a point feature for the location we chose,
and the **Layers Panel** will display a new temporary layer named **Event
location**…  
  


![](media/a3dc7bab5a2f84bdd6c7735ad00d1486.png)

### Edit the existing model

-   In the **Processing toolbox**, expand the **Models** category, then expand
    the **Training** group  
      
    

    ![](media/997aeb612ecc2dcf4bf0993ede7cc33c.png)

-   **Right click** the model named **Affected Buildings**, choose **Edit
    Model…** to open the **Graphical Modeler** window  
      
    

    ![](media/ba2b061ceecba9ada744c1bd82e6295a.png)

### Add input parameter for Road network layer 

Let’s add the input parameter for the road network layer

-   Switch to the **Inputs** panel (use the tabs at the bottom of the Algorithms
    panel)

-   **Double click** the **Vector Layer** input  
      
    Note that a **Parameter Definition** dialog opens

-   Set **Parameter name** to **Road network layer**

-   Set **Geometry Type** to **Line**  
      
    

    ![](media/da32dfa9fdc1726dbf6d6cae7d0c348f.png)

-   Click the **OK** button

-   Re-position the items to look like below…  
      
    

    ![](media/cd64fdc0422500d00fe6cb0c38d90873.png)

-   Save the model by clicking the save tool on the toolbar

### Add input parameter for Travel distance 

Now let’s add the travel distance input parameter

-   **Double click** the **Number** input

-   Set **Parameter name** to **Road network layer**

-   Set **Min value** to **1**

-   Set **Max value** to **10000**

-   Set **Default value** to **200**  
      
    

    ![](media/e802f6a592973302e4d327da3170b178.png)

-   Click the **OK** button

-   Re-position the items to look like below…  
      
    

    ![](media/9b60f40648642d721720321e195658df.png)

-   Save the model by clicking the save tool on the toolbar

### Add algorithm for Service area (from point)

Now well add an algorithm that calculates the service area form the event
location along our road network

-   Switch to the **Algorithms** panel (use the tabs at the bottom of the Inputs
    panel)

-   In the **Algorithms** panel, type **service** in the **search** bar  
      
    Note that the list of algorithms is automatically filtered as we type in the
    search value…  
      
    

    ![](media/fc48a3d2710b4b3ae037297b0e481ba1.png)

-   **Double click** the **Service area (from point)** algorithm  
      
    Note that the **Service area (from point)** properties dialog opens…  
      
    

    ![](media/0873ac0fcf1de07e44d325dbdd113115.png)

-   Set **Vector layer representing network** to **Road network layer**

-   Set **Start point (x, y)** to **Event location**

-   Click the option button next to the **Travel cost** textbox  
      
    Note the **Expression Based Input** dialog window opens…  
      
    

    ![](media/45f587217a2a9b62f6fb4d0466f46096.png)

-   Remove the value **0.0** in the expression panel

-   Double click the **traveldistance** variable in the middle panel  
      
    

    ![](media/91892ba3d24fa6f07b1f57221bf04e7f.png)

-   Click the **OK** button

>   Note that the **Travel cost** is now populated with the variable
>   **\@traveldistance**  
>     
>   

![](media/0f911c67d37388ccc3bd5105b4f2d506.png)

-   Set the **Service area (lines)** to **Affected road network**  
      
    

    ![](media/e3b65af201cc6b53af489f4d2ef29e15.png)

The **Service area (from point)** properties dialog should look like…

![](media/14266297ae28e9b3f438b4bb918e7d6c.png)

-   Click the **OK** button

-   Re-position the items to look like below…  
      
    

    ![](media/01d3031c66fd972ee44c4aefb7e8cef4.png)

-   Save the model by clicking the save tool on the toolbar

### **Add input parameter for road network buffer**

Now let’s add the input parameter for the road network buffer

-   Switch to the **Inputs** panel (use the tabs at the bottom of the Algorithms
    panel)

-   **Double click** the **Number** input

-   Set **Parameter name** to **Travel distance buffer**

-   Set **Min value** to **1**

-   Set **Max value** to **1000**

-   Set **Default value** to **20**  
      
    

    ![](media/52dc28ffbcfec7ee34aa46b181631912.png)

-   Click the **OK** button

-   Re-position the items to look like below…  
      
    

    ![](media/59fee4c0a941d5d93e60bda95710bdcf.png)

-   Save the model by clicking the save tool on the toolbar

### Add algorithm for buffer

Now let’s add the buffer algorithm

-   Switch to the **Algorithms** panel (use the tabs at the bottom of the Inputs
    panel)

-   In the **Algorithms** panel, type **buffer** in the **search** bar  
      
    

    ![](media/cfe1c205bc24aa510ad59a13033cc216.png)

-   **Double click** the QGIS **Buffer** algorithm  
      
    Note that the **Buffer** properties dialog opens…  
      
    

    ![](media/c3d87f4dee203d6df4d6986ec483515d.png)

-   Set **Input layer** to **'Service area (lines)' from algorithm 'Service area
    (from point)'**  
      
    

    ![](media/bf2adaac0f04cb776bbebcb69e8dff70.png)

-   Click the option button next to the **Distance** textbox  
      
    Note the **Expression Based Input** dialog window opens…  
      
    

    ![](media/81af285a59f1c0e6dbe9d90657b07b9d.png)

-   Remove the value **10** in the expression panel

-   Double click the **traveldistancebuffer** variable in the middle panel  
      
    

    ![](media/4ba0f30e5de18a4ec066a3ea0a635310.png)

-   Click the **OK** button

-   Note that the **Distance** is now populated with the variable
    **\@traveldistancebuffer**  
      
    

    ![](media/035b992539612bf2225bab5b2bcf8f3c.png)

-   Set **Buffered** to **Travel distance buffer**  
      
    

    ![](media/a88cd72eb27ae9e1a780a696747972db.png)

The **Buffer** properties dialog should look like…

![](media/20bc557a611dec31778ee7d9e9f16823.png)

-   Click the **OK** button

-   Re-position the items to look like below…  
      
    

    ![](media/7dafc2744510436087d73b2e4a03c566.png)

-   Save the model by clicking the save tool on the toolbar

### **Add input parameter for land parcel layer**

Now let’s add the input parameter for the land parcel layer

-   Switch to the **Inputs** panel (use the tabs at the bottom of the Algorithms
    panel)

-   **Double click** the **Vector Layer** input  
      
    Note that a **Parameter Definition** dialog opens

-   Set **Parameter name** to **Land parcel layer**

-   Set **Geometry Type** to **Polygon**  
      
    

    ![](media/d3c8049e81b5d06539500fedd04be45d.png)

-   Click the **OK** button

-   Re-position the items to look like below…  
      
    

    ![](media/39281f148ca28ee30c6df9929465b079.png)

-   Save the model by clicking the save tool on the toolbar

### Add algorithm for extracting by location for land parcels

Now let’s add the extract by location algorithm

-   Switch to the **Algorithms** panel (use the tabs at the bottom of the Inputs
    panel)

-   In the **Algorithms** panel, type **extract by** in the **search** bar  
      
    

    ![](media/8fcc6ba8c12a2ece94f572ffb2773bc9.png)

-   **Double click** the **Extract by location** algorithm  
      
    Note that the **Extract by location** properties dialog opens…  
      
    

    ![](media/99fefd5581be3e8c06bb65715e6887e4.png)

-   Set **By comparing to the features from** to **'Buffered' from algorithm
    'Buffer'**  
      
    

    ![](media/30f96fa1900a70ff8f3cb5da5c34fe3e.png)

The **Extract by location** properties dialog should look like…

![](media/9c28c9069906f39cd74d7b23a451f818.png)

-   Click the **OK** button

-   Re-position the items to look like below…  
      
    

    ![](media/ab41a81b9076c28d8971de154c9be410.png)

-   Save the model by clicking the save tool on the toolbar

### **Add input parameter for building footprints layer**

Now let’s add the input parameter for the building footprints layer

-   Switch to the **Inputs** panel (use the tabs at the bottom of the Algorithms
    panel)

-   **Double click** the **Vector Layer** input  
      
    Note that a **Parameter Definition** dialog opens

-   Set **Parameter name** to **Buildings footprints layer**

-   Set **Geometry Type** to **Polygon**  
      
    

    ![](media/427b16d92a8f67a9591083fb4d4d9095.png)

-   Click the **OK** button

-   Re-position the items to look like below…  
      
    

    ![](media/032e41e7dac6724baad50e9dd9ee89ad.png)

-   Save the model by clicking the save tool on the toolbar

### Add algorithm for extracting by location for building footprints

Now let’s add the extract by location algorithm

-   Switch to the **Algorithms** panel (use the tabs at the bottom of the Inputs
    panel)

-   In the **Algorithms** panel, type **extract by** in the **search** bar  
      
    

    ![](media/8fcc6ba8c12a2ece94f572ffb2773bc9.png)

-   **Double click** the **Extract by location** algorithm  
      
    Note that the **Extract by location** properties dialog opens…  
      
    

    ![](media/cb898d2f050e8a0ebbffe4352ca6ed92.png)

-   Set **By comparing to the features from** to **'Extracted (location)' from
    algorithm 'Extract by location'**  
      
    

    ![](media/75857bb583e7c9dc30e52d45e179872a.png)

-   Set **Extracted (location)** to **Affected buildings**  
      
    

    ![](media/98adef9528fd049111757ea3511e75f2.png)

The **Extract by location** properties dialog should look like…

![](media/995568df62baf21454499aa142c5fa25.png)

-   Click the **OK** button

-   Re-position the items to look like below…  
      
    

    ![](media/121ac3c3e3a4870ea90d216904fa49f8.png)

-   Save the model by clicking the save tool on the toolbar

### Running the model

We now have our processing model completed – let’s run the model.

-   Close the **Processing Modeler** window

-   In the **Layers panel** remove the layer named **Event Location** from our
    previous testing.

-   In the **Processing toolbox**, expand the **Models** category, then expand
    the **Training** group  
      
    

    ![](media/997aeb612ecc2dcf4bf0993ede7cc33c.png)

-   **Double click** the model named **Affected Buildings**  
      
    Note that Affected Buildings dialog is displayed…  
      
    

    ![](media/6d47b9fe44548298b593fae7e44d0aa0.png)

-   Click the

    ![](media/45f892ea216e2a3872322a81b6c0a167.png)

    option button next to the **Event location (x, y)** textbox  
      
    Note that we are switched to the **Map Canvas** and we can click a location
    for the event on the Map Canvas.  
      
    **Click a location** as indicated below on the **Map Canvas**…  
      
    

    ![](media/6aec8dddaf1f0a6feb8fba78475821d2.png)

The **Event location (x, y)** textbox will now be populated with the coordinates
of the location we clicked on the Map Canvas

-   Set **Buildings footprints layer** to
    **Wairoa_Vector_Buildings_SwimmingPools**  
      
    

    ![](media/c213914972cf7e7878a4cea86ee4d8e0.png)

-   Set **Land parcel layer** to **nz_primary_land_parcels**  
      
    

    ![](media/cabef06b662aa7a9b8d92f55bcb6a50a.png)

-   Set **Road network layer** to **nz_roads_addressing**  
      
    

    ![](media/613ec9264587a19a4924c931545aab03.png)

-   Click the **Run** button

-   When the **Coordinate Reference System Selector** dialog opens, click the
    **OK** button  
      
    

    ![](media/802db11a77491e9bca2f8c5c3d2536bd.png)

-   In the **Affected Buildings** dialog, click the **Close** button

The **Map Canvas** should now show the results of the **Affect buildings**
processing model…

![](media/a6eb2fa044bd646fc3a7574b30e10996.png)

### Setting styles for the output layers

Whenever the **Affected Buildings** model is run the output layers styles are
determined randomly by QGIS.

We can extend our model by applying a QGIS **.qml** style file to each layer
output

We have the following pre-defined style files:

-   C:\\Training\\AffectedBuildings_event_location.qml

-   C:\\Training\\AffectedBuildings_travel_distance_buffer.qml

-   C:\\Training\\AffectedBuildings_affected_road_network.qml

-   C:\\Training\\AffectedBuildings_affected_buildings.qml

These style files define the following styles:

![](media/eb212388ab94061ec861e2bc2b3b6c9f.png)

Let’s start editing our model

-   In the **Processing toolbox**, expand the **Models** category, then expand
    the **Training** group  
      
    

    ![](media/997aeb612ecc2dcf4bf0993ede7cc33c.png)

-   **Right click** the model named **Affected Buildings**, choose **Edit
    Model…** to open the **Graphical Modeler** window  
      
    

    ![](media/ba2b061ceecba9ada744c1bd82e6295a.png)

Add the Event Location style

-   In the **Algorithms** panel, type **style** in the **search** bar  
      
    

    ![](media/024e9c6fa04b9871fbd4a96da939bcb5.png)

-   **Double click** the **Set style for vector layer** algorithm  
      
    Note that the **Set style for vector layer** properties dialog opens…

-   Set **Vector layer** to **'Output layer' from algorithm 'Pick point on
    map'**

-   Set **Style file** to **C:\\Training\\AffectedBuildings_event_location.qml**  
      
    

    ![](media/e5d0f8e18fa58e6c89b313b6bbbd372e.png)

-   Click the **OK** button

-   Re-position the items

Add the Affected road network style

-   **Double click** the **Set style for vector layer** algorithm

-   Set **Vector layer** to **'Service area (lines)' from algorithm 'Service
    area (from point)'**

-   Set **Style file** to
    **C:/Training/AffectedBuildings_affected_road_network.qml**  
      
    

    ![](media/14f3bf0c2188a60c852a2192a4e4a107.png)

-   Click the **OK** button

-   Re-position the items

Add the Travel distance buffer style

-   **Double click** the **Set style for vector layer** algorithm

-   Set **Vector layer** to **'Buffered' from algorithm 'Buffer'**

-   Set **Style file** to
    **C:/Training/AffectedBuildings_travel_distance_buffer.qml**  
      
    

    ![](media/87c28f89b1d8f1c474117de21f3bfa44.png)

-   Click the **OK** button

-   Re-position the items

Add the Affect buildings style

-   **Double click** the **Set style for vector layer** algorithm

-   Set **Vector layer** to **'Extracted (location)' from algorithm 'Extract by
    location'**

-   Set **Style file** to
    **C:/Training/AffectedBuildings_affected_buildings.qml**  
      
    

    ![](media/1556adad7836bf2a61c45c695c6a3de8.png)

-   Click the **OK** button

-   Re-position the items

Our model should look like this now…

![](media/e03bdfc55353bf6a3a6f2b154872d41a.png)

-   Save the model by clicking the save tool on the toolbar

### Running the final model with styling

We now have our processing model completed – let’s run the model.

-   Close the **Processing Modeler** window

-   In the **Layers panel** remove the layers from previous running of the model

    -   **Event Location**

    -   **Affected road network**

    -   **Travel distance buffer**

    -   **Affected buildings**

-   In the **Processing toolbox**, expand the **Models** category, then expand
    the **Training** group  
      
    

    ![](media/997aeb612ecc2dcf4bf0993ede7cc33c.png)

-   **Double click** the model named **Affected Buildings**  
      
    Note that Affected Buildings dialog is displayed…  
      
    

    ![](media/6d47b9fe44548298b593fae7e44d0aa0.png)

-   Click the

    ![](media/45f892ea216e2a3872322a81b6c0a167.png)

    option button next to the **Event location (x, y)** textbox  
      
    Note that we are switched to the **Map Canvas** and we can click a location
    for the event on the Map Canvas.  
      
    **Click a location** as indicated below on the **Map Canvas**…  
      
    

    ![](media/6aec8dddaf1f0a6feb8fba78475821d2.png)

The **Event location (x, y)** textbox will now be populated with the coordinates
of the location we clicked on the Map Canvas

-   Set **Buildings footprints layer** to
    **Wairoa_Vector_Buildings_SwimmingPools**  
      
    

    ![](media/c213914972cf7e7878a4cea86ee4d8e0.png)

-   Set **Land parcel layer** to **nz_primary_land_parcels**  
      
    

    ![](media/cabef06b662aa7a9b8d92f55bcb6a50a.png)

-   Set **Road network layer** to **nz_roads_addressing**  
      
    

    ![](media/613ec9264587a19a4924c931545aab03.png)

-   Click the **Run** button

-   When the **Coordinate Reference System Selector** dialog opens, click the
    **OK** button  
      
    

    ![](media/802db11a77491e9bca2f8c5c3d2536bd.png)

-   In the **Affected Buildings** dialog, click the **Close** button

The **Map Canvas** should now show the results of the **Affect buildings**
processing model with our style files applied to each output layer…

![](media/4bc9d0c0a43c32e9dfc60274015e0d19.png)

![](media/eb212388ab94061ec861e2bc2b3b6c9f.png)

### Editing model help

We can document our models from within the graphical modeler itself.

To document our **Affected Buildings** model, let’s start by editing our model

-   In the **Processing toolbox**, expand the **Models** category, then expand
    the **Training** group  
      
    

    ![](media/997aeb612ecc2dcf4bf0993ede7cc33c.png)

-   **Right click** the model named **Affected Buildings**, choose **Edit
    Model…** to open the **Graphical Modeler** window  
      
    

    ![](media/ba2b061ceecba9ada744c1bd82e6295a.png)

Now let’s edit the model help

-   In the **Graphical Modeler** window, click the

    ![](media/575c3e2641824a18a8ef5c8aab24a023.png)

    **Edit model help** tool on the toolbar  
      
    Note that **Help Editor** dialog opens…  
      
    

    ![](media/ab9565e8ca7384ecab17199389c8eaf4.png)

-   Select the element named **Algorithm description** in the **Select element
    to edit panel**  
      
    

    ![](media/58e5acf74a8b729c1ab7aab998990f37.png)

-   Click inside the **Element Description** panel, and **type a description**
    for the model  
      
    TIP – Copy and paste the text saved in the file
    C:\\Training\\AffectedBuildings_help_text.txt  
      
    

    ![](media/2c2c9aa037c20e6be83eec4e015bb031.png)

-   Click the **OK** button

-   In the **Graphical Modeler** window, click the

    ![](media/a78d4b8893db6795a2b33ee7509be84f.png)

    **Run model** tool on the toolbar

>   Note that the Model now displays a description panel on the right-hand side
>   of the model dialog…

![](media/8e2fdc65917844ca1281345078e4ac9b.png)

-   Click the **Close** button

-   Save the model by clicking the save tool on the toolbar
