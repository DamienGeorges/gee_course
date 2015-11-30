---
title: "GEE Practicals"
author: "Damien g."
date: "10/11/2015"
output:
  ioslides_presentation:
    css: style.css
    incremental: no
    logo: ~/Work/GEE_COURSE/geecourseshub/materials/figures/AU_GEE_logo_square.png
    smaller: yes
    widescreen: yes
    md_extensions: +hard_line_breaks+footnotes
---

## Important note

A lot of slides, text, images, examples have been **peered from GEE core team folks'** presentations.  

You can find the original documents here:  

[http://earthenginesummit2015.earthoutreach.org/training-materials](http://earthenginesummit2015.earthoutreach.org/training-materials)

# Overview of what we will (try) to do today

## GEE practical overview {.build}

**Aim:** The aim of this practical is to make you **discover GEE** and associated tools, to make you an 
*autonomous* GEE  user and **play** a bit with GEE features.

<div>
- connect to your GEE account
- data catalog / workspace / help page / GEE developer group / Fusion Table / GEE API    
<br></br>
</div>

<div>
- visualize a map into your workspace
- exporting an image from workspace
- identify where you can find help
- ...
<br></br>
</div>

<div>
- create a fusion table
- importing points location into GEE
- write a simple GEE script
- import / extract / process / export available images
- ... 
</div>

<div class="notes">
1. connecting to your account, discovering features
2. user friendly part (catalogue, workspace)
3. coding part (playground)
</div>

# Discovering of GEE

# List of usefull tools

## Connecting to GEE account {.build}

Open a Web browser (Chrome or Firefox) and open the following links in different tabs:

> - [GEE main page](https://earthengine.google.org)
> - [GEE help page](https://developers.google.com/earth-engine/)
> - [GEE Google Group](https://groups.google.com/forum/?fromgroups#!forum/google-earth-engine-developers)
> - [GEE Playground](https://ee-api.appspot.com/)
> - [Google Drive](https://drive.google.com/drive/my-drive)
> - [Google Fusion Table (help page)](https://support.google.com/fusiontables/answer/2571232)

<div class="red2">
**I recommand you to bookmark all this pages!**
</div>

# The data catalogue

## Discover GEE main page | [https://earthengine.google.org](https://earthengine.google.org) {.build}

> - Visualize some products done with GEE:
>     + visualize time laps video / web app (e.g. [Brazil deforestation](https://earthengine.google.org/#intro/Amazon))
>     + visualize precomputed data (e.g. [10km buffered roadless map](https://earthengine.google.org/#intro/Roadless10km))

## Discover the Data Catalogue | [https://earthengine.google.org](https://earthengine.google.org) {.build}

Try to find the **MODIS 16 days NDSI product**.  

- is it easy to find this product?  
- are you able to find image collection id?  
- can you find any extra information about this product?   

## Discover the Data Catalogue | [https://earthengine.google.org](https://earthengine.google.org) {.build}

Here is the link to the [MODIS 16 days NDSI product in the catalogue](https://earthengine.google.org/#detail/MODIS%2FMCD43A4_NDSI) and [detailed information](https://lpdaac.usgs.gov/dataset_discovery/modis/modis_products_table/mcd43a4) given by the provider (and even a bit more [here](https://www.umb.edu/spectralmass/terra_aqua_modis/v006/mcd34a4_nbar_product) ).

- search for "MODIS 16 days NDSI" in the search bar
- display the image collection summary
- click on the "Provider link" to get more info

<div class="columns-2">
<img src="../materials/figures/GEE_Screenshot_6.png" width=80%>
 
<img src="../materials/figures/GEE_Screenshot_7.png" width=80%>
</div>

<div class="red2">
**Are you satisfied with the given information?**
</div>

<div class="notes">
  - a bit difficult to find the exact way MCD43A4 NDVI and NDSI have been produced.. no link to publication. (what is the exact function?)
</div>

## Discover the Data Catalogue | [https://earthengine.google.org](https://earthengine.google.org) {.build}

> - Is there some other Normalized Difference Snow Index product available?
>     + how many porducts are available?
>     + from what sources of data NDSI have been derived?
>     + what is the finest time scale I can use if I want to conduct a study covering 1990 - 2010 period?
>     + could you find detailed information on the product of interest? (product name, resolution, quality, ...)

> - Could you do the same with a landcover product? 
>     + Do you manage to find information of how it has been computed? references? 

<div class="red2">
**Take a moment to explore the catalogue..**
</div>

<div class="notes">
- search for "NDSI" in the data catalog
- 15 (+ 2) NDSI products
- derived from MODIS and LANDSAT imagery
- over 1990 - 2010 the best time resolution is 8 day with LANDSAT 5 (30m resolution)
- it seems to be difficult to find detailed info for this particular product (have to go to USGS website [](http://landsat.usgs.gov/about_landsat5.php) )
</div>

## Discover the Data Catalogue | [https://earthengine.google.org](https://earthengine.google.org){.build}

**Note:** Instead of making "classical" search in the catalog, that could be sometimes useful to use the data tags to do a more accurate research.

Try to search for **"quality"** and **"tag:quality"**. Do you notice any difference? 

# The workspace

## Discover the Workspace / Explorer | [https://earthengine.google.org](https://earthengine.google.org)

<div class="red2">
The workspace is (according to me) only relevant for fast catalog data visualization (and export).  
If you want to analyse/transform/combine images you will rapidly be limited  
**&#10140; GEE Playgroung**
</div>

## Discover the Workspace | Ex1: Load, filter and export an image

**Aim:** Exporting the latest 16-days MODIS NDVI keeping only high quality observation over Spain.

Workflow:

1. Load MODIS 16 Days NDVI product
2. Load MODIS 16 Days quality band product
3. Create a mask to filter out all non high quality points
4. Apply the mask
5. Export the filtered MODIS 16 days NDIVI image

<div id="gee_link"> (https://explorer.earthengine.google.com/#workspace/GaqNPpCUUkl) </div> 


## Discover the Workspace | Ex2: Create a slope and aspect map

**Aim:** Create a nice slope map for the alpine arc.

Workflow:

1. Load the SRTM 30m digital elevation product
2. Produce the slope and aspect maps
3. Display the slope map in a nice way
4. Export an image of the slope map of alpine arc (as .jpg)

<div id="gee_link"> (https://explorer.earthengine.google.com/#workspace/wDkCpce1rJq) </div> 

# The Fusion Table

## What is Fusion Table? {.build}

<div>
- A fusion table is a **georederenced table** where each row contains:  
    + **location** information in WGS84 (compulsory)  
    + at least a **numeric** arg that should be use to set up **classes** (compulsory)  
    + whatever other information (text, pictures, objects, ...) (optional)  
</div>

<div>
- You can **create** a fusion table [here](https://support.google.com/fusiontables/answer/2571232)  
</div>

<div>
- Fusion tables are the **easiest way** to include sites specific **location within GEE**.  
</div>

<div class="red2">
The FT has to be public for the whole web to be accessible in GEE
</div>

## Create a Fusion Table 

**Aim:** Create a fusion table and import it in GEE workspace.


**Workflow:**  

1. Download/create a .csv file  
**note:** this file should contain at least sites locations (WGS84) and a numerical value that can be used as classifier (e.g. [this file](https://drive.google.com/open?id=0B9E3DXffjxAxMzlyOUdJNjRRa2s) where we should use elevation to classify sites)
2. Go to [Google Fusion Table web page](https://support.google.com/fusiontables/answer/2571232) and upload the .csv file
3. define/check that location info are well defined
4. make the FT available on the web
4. try to import the FT in GEE workspace to be sure that it is working



# The playground / API

## Discover the GEE API

- try to find where you can find :
    + code examples
    + help files
    + your scripts
    + ...

- create a new file/folder and save it, rename it, ...

- go to [GEE help page](https://developers.google.com/earth-engine/) and search for tutorial and other examples of code, run them, enjoy them ;)

<div class="red2">
**A lot of material is available here! To use without moderation**
</div>

## Discover the GEE API

Here start serious things..  :)  

The aim here is to show you some (far to be exhaustive) of simple things you can do
in GEE API based 2 examples: 

> - extract MODIS NDVI for some site location of interest
> - create a map of the trends in MODIS summer NDVI (peak) for Canada. 


# GEE API examples

## Discover the GEE API | extract MODIS NDVI for some sites {.build}

**Aim:** Get the values of MODIS NDVI (16 day product) from March to November 2013 at our sites location (stored in a Fusion Table).

This example will cover the following steps:

> - load an Image collection  
> - extract a subset of images from an image collection (filter by date)
> - load a Fusion Table containing sites location  
> - display the sites location over a computed image  
> - extract values for a list of sites location  
> - export the extracted values as a csv  

**Bonus:**  
- Extract Mean NDVI values over buffer around sites  
- Produce a simple charts (Evolution of mean NDVI over time and sites)

<div>
Below is the link to scripts that does the job:  

<div id="gee_link"> (https://code.earthengine.google.com/bac5fb1b9332237eda076a10cbb14e8f) </div> 
</div>


## Discover the GEE API | trends in summer NDVI example {.build .smaller}

**Aim:** Create a map of trend of MODIS summer NDVI (peak of NDVI) over Canada.

<div class="columns-2">
In this example, we will see how to:

> - load a Fusion Table
> - extract polygon from a Fusion Table (countries boundaries)
> - load an collection of image (MODIS 16 Days NDVI)
> - filter an image collection (by date and location)
> - load a simple image (MODIS yearly Land Coveer)
> - create a function (calculation of peak of NDVI by year)
> - apply/map a function (peak of NDVI / trend in NDVI peak (linear fit))
> - create an image / an image collection (trend in NDVI peak)
> - transform an image (mask, ...)
> - display an image
> - export an image
</div>

## Discover the GEE API | trends in summer NDVI example {.build}

<div>
**Bonus:**  
Evaluate MODIS 16 days product according to associated quality flags  

> - filter MODIS NDVI (keep only high quality data)  
> - map indexs to qualify the quality of created images  
    + average number of observation used to calculate a NDVI peak  
    + number of NDVI peaks used to estimate the trend  
</div>

<div>
Below are the links to scripts that do the job :  

<div id="gee_link"> (https://code.earthengine.google.com/1676b5da712b05686745f261fbfac00f) </div>

<div id="gee_link"> (https://code.earthengine.google.com/563e86500450d0c58b842e56c3a75771) </div>

</div>


# Some concepts/tricks before to start

## JavaScript Scripting Basics {.build .smaller}

> - variables and comments

```javascript
### <b>
// simple variable definition 
var name = "damien";
### </b>
print(name);
```

> - functions

```javascript
// this is function
var myCalculation = function(first, second) {
  var numerator = first + second;
  var quotient = numerator / first;
  return quotient;
};
// you call it like that
var myResult = myCalculation(10, 2);
```

> - objected linked functions

```javascript
var image1 = ee.Image('my_image')
var image2 = ee.Image('my_mask')
###<b>
// here we apply the function mask to a ee.Image object
var image3 = image1.mask(image2)
### </b>
```

## GEE Javascript library

<div class="columns-2">
a lot of:
- objects (i.e. **ee.XXX**) 
- and of associated functions..

```javascript
// Select the forest classes from the MODIS 
// land cover image

var cover = ee.Image('MCD12Q1/MCD12Q1_005_2001_01_01')
    .select('Land_Cover_Type_1');
```

<img src="../materials/figures/GEE_Screenshot_10.png" width=80%>
</div>

<div id="gee_link"> (https://ee-api.appspot.com/4ce4190ca053a9649cfb39cb14fa22f4) </div> 

## GEE API basics tricks | load an image and select a band

```javascript
// Select the forest classes from the MODIS 
// land cover image
var all_land_cover = ee.Image('MCD12Q1/MCD12Q1_005_2001_01_01');
// select a band
var cover = all_land_cover.select('Land_Cover_Type_1');
print(cover);
```

<div id="gee_link"> (https://ee-api.appspot.com/4ce4190ca053a9649cfb39cb14fa22f4) </div> 

## GEE API basics tricks | display an image

```javascript
// Select the forest classes from the MODIS land cover image
var all_land_cover = ee.Image('MCD12Q1/MCD12Q1_005_2001_01_01');
    
// print the image summary in the console
print(all_land_cover);

// select a band
var cover = all_land_cover.select('Land_Cover_Type_1');
print(cover);

### <b>
// display the selected band 
Map.addLayer(cover, {},'land cover');
### </b>
```

more tricks [here](https://developers.google.com/earth-engine/image_visualization)

<div id="gee_link"> (https://ee-api.appspot.com/4ce4190ca053a9649cfb39cb14fa22f4) </div> 

## GEE API basics tricks | load an image collection and apply a filter

```javascript
// Filter to only include images within the colorado and utah boundaries.
var polygon = ee.Geometry.Polygon([[
  [-109.05, 37.0], [-102.05, 37.0], [-102.05, 41.0],   // colorado
  [-109.05, 41.0], [-111.05, 41.0], [-111.05, 42.0],   // utah
  [-114.05, 42.0], [-114.05, 37.0], [-109.05, 37.0]]]);

// Create a Landsat 7 composite for Spring of 2000, and filter by
// the bounds of the FeatureCollection.
var collection = ee.ImageCollection('LE7_L1T')
    .filterDate('2000-04-01', '2000-07-01')
    .filterBounds(polygon);
```
 
Here we are selecting all the image from the Landsat 7 collection and keeping only
images within the boundaries of a define polygon between 2 dates.

<div class="red2">
**Go in the documentation and see the variety of filters you can apply to 
ee.Image and ee.ImageCollection**
</div>

<div id="gee_link"> (https://ee-api.appspot.com/4ce4190ca053a9649cfb39cb14fa22f4) </div>

# GEE reducers

## Reduce image bands to image

<div class="columns-2">
```javascript
var max = image.reduce(ee.Reducer.max());
```

<img src="../materials/figures/GEE_reducer_image.png" width=80%>
</div>

<div id="gee_link"> (https://ee-api.appspot.com/199620453c67c2d88d66058eed5d81aa) </div>

## Reduce image collection to image

<div class="columns-2">
```javascript
// reduce the collection
var median = ndviCollection.reduce(ee.Reducer.median());
```

<img src="../materials/figures/GEE_reducer_image_collect.png" width=80%>
</div>

<div id="gee_link"> (https://ee-api.appspot.com/b4724841aa1358dd3bcf478d2b0f3448) </div>

## Reduce Image to statistics

<img src="../materials/figures/GEE_reducer_image_stat.png" width=80%>

```javascript
var mean = image.reduceRegion({
  reducer: ee.Reducer.mean(),
  geometry: region.geometry(),
  scale: 30,
  maxPixels: 1e9,
  bestEffort: true,
  });
```

<div class="red2">
**And lot more..**
</div>

<div id="gee_link"> (https://ee-api.appspot.com/84f6911ff955af2a7b45cee61bfaeb0e) </div>


## Some other reducers..

<img src="../materials/figures/GEE_reducer_list.png" width=80%>

# Let's practice!! 

# Example 1: extract MODIS NDVI for some sites

## Discover the GEE API | extract MODIS NDVI for some sites {.build}

**Aim:** Get the values of MODIS NDVI (16 day product) from March to November 2013 at our sites location (stored in a Fusion Table).

My proposition to do it is available [here](https://code.earthengine.google.com/bac5fb1b9332237eda076a10cbb14e8f) but it would be better if you try to do it yourself ;)

Some advise in the next slides...

## Discover the GEE API | extract MODIS NDVI for some sites {.build}

Load an MODIS NDVI 16 days image collection

<div id = 'trick'>
 - search for "MODIS NDVI" to find the good product
 - you can use the *import* functionality
 - check the standard code genereted
</div>


## Discover the GEE API | extract MODIS NDVI for some sites {.build}

Filter the image collection to keep only the images from March to November 2013

<div id = 'trick'>
 - use a the filter filterDate (check helpfile)
 - you can check this [example](https://code.earthengine.google.com/e68337a29aa964b89ac60704babfd1c5)
 - print the filtered object and check that the filter is effective
</div>

## Discover the GEE API | extract MODIS NDVI for some sites {.build}

Load a Fusion Table containing your sites location

<div id = 'trick'>
 - you can use the research dataset field or use `ee.FeatureCollection('ft:...') function.
 - you can check this [example](https://code.earthengine.google.com/e68337a29aa964b89ac60704babfd1c5)
 - print the filtered object and check that the filter is effective
</div>

## Discover the GEE API | extract MODIS NDVI for some sites {.build}

Compute the maximum NDVI over the periode

<div id = 'trick'>
 - we want here to create an image from an Image collection
 - use an `ee.ImageCollection`'s reducer (max)
 - you can ensure the type of output by casting the output of the reducer (e.g. `ee.Image`)
</div>

## Discover the GEE API | extract MODIS NDVI for some sites {.build}

Display the sites location over a computed image

<div id = 'trick'>
 - use `Map.addLayer` function
 - add first the image then the points
 - you can play with graphical parameters (palette, alpha, scale, ...)
 - you can give a name to each layer (see `Map.addLayer` help section)
</div>

## Discover the GEE API | extract MODIS NDVI for some sites {.build}

Extract values for a list of sites location

<div id = 'trick'>
 - you have to apply a function to each image of the collection (map)
 - then you have to extract the value for all your location. You can use the ee.Image `reduceRegions` reducer.
 - it is laways a good idea to print the results of this function
</div>

## Discover the GEE API | extract MODIS NDVI for some sites {.build}

Export the table as a csv

<div id = 'trick'>
 - you have to use `Export.table` function
 - you have to transform your `ee.FeatureCollection` of `ee.FeatureCollection` into a simple `ee.FeatureCollection` &#10140; `flatten()`
 - you can specify the name of the file and the output directory
 - check the results you obtain in your Google Drive
</div>

## Discover the GEE API | extract MODIS NDVI for some sites {.build}

Try to redo the extraction working with all the NDVI values for 2013..

Do you remark something?

<div class="red2">
**important note**: if the first value of the firt site for a propriety is null then it will be removed from the exported table!!
</div>

## Discover the GEE API | extract MODIS NDVI for some sites {.build}

BONUS1: Extract Mean NDVI values over buffer around sites  

<div id = 'trick'>
  - you have to map the function buffer to all your sites locations
  - you can refer to the [FeatureCollection > buffer example](https://code.earthengine.google.com/0ca3ea59cad2a01f5653e6c76c271df8) 
</div>


## Discover the GEE API | extract MODIS NDVI for some sites {.build}

BONUS2: Produce a simple charts (Evolution of mean NDVI over time and sites

<div id = 'trick'>
  - you can refer to this [example](https://developers.google.com/earth-engine/charts_image_series_by_region) in the developer help page that is very similar. 
</div>

# Example 2: trends in summer NDVI

## Discover the GEE API | trends in summer NDVI example {.build .smaller}

**Aim:** Create a map of trend of MODIS summer NDVI (peak of NDVI) over Canada.


My proposition to do it is available [here](https://code.earthengine.google.com/1676b5da712b05686745f261fbfac00f) but it would be better if you try to do it yourself... Or at least the first parts ;)

Some advise in the next slides...

## Discover the GEE API | trends in summer NDVI example {.build .smaller}

Load countries boundaries Fusion Table and keep only Canada boundaries.

<div id = 'trick'>
  - 'ft:1tdSwUL7MVpOauSgRzqVTOwdfy17KDbw-1d9omPw' is a Fusion Table containing polygons of countries boundaries
  - keep only Canada boundaries Feature using `filterMetadata` filter
  - to reduce a `FeatureCollection` containinf a single `Feature` to a simple `Feature` object, you can use the function first()
</div>

```javascript
// 1. load countries boundaries table
var countries_bounds = ee.FeatureCollection('ft:1tdSwUL7MVpOauSgRzqVTOwdfy17KDbw-1d9omPw');
var canada_bounds = ee.Feature(countries_bounds.filterMetadata('Country', 'equals', 'Canada').first());
print(canada_bounds);
```

## Discover the GEE API | trends in summer NDVI example {.build .smaller}

Load modis 16 days ndvi composit and keep only summer values for canada

<div id = 'trick'>
  - modis 16 days ndvi is located here 'MODIS/MCD43A4_NDVI' 
  - to filter by year and month you can use  `ee.Filter.calendarRange` filter
  - to keep only a geographical part of a collection you can use the `filterBounds` filter that need a `geometry` as argument (point or polygon).
</div>

```javascript
var mcd43a4_ndvi = ee.ImageCollection('MODIS/MCD43A4_NDVI')
  .filter(ee.Filter.calendarRange(6, 8, 'month'))
  .filter(ee.Filter.calendarRange(2001, 2013, 'year'))
  .filterBounds(canada_bounds.geometry());
print(mcd43a4_ndvi);
```

## Discover the GEE API | trends in summer NDVI example {.build .smaller}

Load MCD12Q1 Land Cover Type Yearly Global 500m for the year 2012 and keep only the water mask.

<div id = 'trick'>
  - you can load a single image from a Image collection given the *full path* to this image (e.g. *MODIS/051/MCD12Q1/2012_01_01*)
  - you can keep only selected bands of an image using `select` function.
</div>

```javascript
var mcd12q1_landcover = ee.Image('MODIS/051/MCD12Q1/2012_01_01').select(0)
// note: this landcover map will be used as mask to remove non land areas
```

## Discover the GEE API | trends in summer NDVI example {.build .smaller}

Calculate the annual summer ndvi

<div id = 'trick'>
  - you have to define your own function (e.g. `peak_by_year`) that will return the maximal NDVI image for a selected set of images (associated to a given year)
  - you candefine sequence of number with `ee.List.sequence`
  - you can set/get properties of objects with `set` and `get`
  - use `map` to apply a function over a list of 'input' parameter
</div>

```javascript
// define the year we want to study
var yr_intersect = ee.List.sequence(2001, 2013, 1);

// define function to calculate anual average
var peak_by_year = function(yr_){ 
    return( mcd43a4_ndvi.filter(ee.Filter.calendarRange(yr_, yr_, 'year')).select(0).max()
    .set('stat', 'peak of ndvi')
    .set('period', 'summer')
    .set('year', yr_) )
}

// calculate the peak summer ndvi
var mcd43a4_ndvi_byYear = ee.ImageCollection.fromImages(yr_intersect.map(peak_by_year))
```


## Discover the GEE API | trends in summer NDVI example {.build .smaller}

Here we want to calculate the linear trend in MODIS summer peak of NDVI.

<div id = 'trick'>
You can refer to the example [Image Collection > Linear Fit](https://code.earthengine.google.com/a0432be6e15003ee35fcff5fac4e10d6) to see how it should be done.
</div>

To be able to compute a linear fit over our NDVI peaks maps, will have to add
a band containing year information to each image.

<div id = 'trick'>
  - you have to define your own function (e.g. `createTimeBand`) that will return the maximal NDVI image for a selected set of images (associated to a given year)
      + your function  should return the original image with a additional band (use `addBands`)
      + it is always a good idea to cast numerical varibales when you can to prevent for useless space consumtion (e.g. here years are integers between 0 and 12)
</div>

```javascript
// Define a function to add the year band to all the image of our collection
function createTimeBand(img) {
  var year = ee.Number(img.get('year')).subtract(2001);
  return ee.Image(year).byte().addBands(img);
}
mcd43a4_ndvi_byYear = mcd43a4_ndvi_byYear.map(createTimeBand);
// Fit a linear trend to the nighttime lights collection.
var fit_peak = mcd43a4_ndvi_byYear.reduce(ee.Reducer.linearFit());
```

## Discover the GEE API | trends in summer NDVI example {.build .smaller}

In this example we only want to focus on slope (*scale* band) over non-water area

<div id = 'trick'>
  - keep only the band you are interested in (`scale`)
  - mask the water area using the MODIS landcover mask we loaded before (maybe you will have to transform this water mask before to apply it ;) )
</div>

```javascript
// Keep only slope information and mask all the water area
var slopes_peak = fit_peak.select('scale').mask(mcd12q1_landcover.neq(0));
```

## Discover the GEE API | trends in summer NDVI example {.build .smaller}

Now we can visualize the map we produced

<div id = 'trick'>
  - you can center the viewport using `Map.setCenter`
  - you can dispaly the map of slopes with `Map.addLayer`
  - if you want to clip an image to a given extent you can use `clip` function
  - it is also possible to define your own visulisation settings (color palette, scale, transparancy, ...)
  - a super cool website to create color palette is [http://colorbrewer2.org/](http://colorbrewer2.org/)
</div>


```javascript
// 4. Display the image

// define a brown to green palette
var diverging_palette = ['8c510a','bf812d','dfc27d','f6e8c3','f5f5f5','c7eae5','80cdc1','35978f','01665e']

// Center our map roughly on canada
Map.setCenter(-100, 70, 3);

// Display trends in NDVI on a brown green scale
Map.addLayer(slopes_peak.clip(canada_bounds), 
  {min: - 0.02 , max: 0.02 , palette: diverging_palette}, 'trends in summer peak NDVI (units/year)');
```

## Discover the GEE API | trends in summer NDVI example {.build .smaller}

The last step is to export the created image.

<div id = 'trick'>
  - you should use `Export.image` function (see help file and examples)
  - it is convenient to define the output file name and directory
  - if you want to change the coordinate of the image you can use the *OGC WKT* version (can be find for most of projection system on [http://spatialreference.org](http://spatialreference.org))
  - in case the image is too big you should maybe thing to transform and cast your values (e.g. multiply by  1000 and convert into integer)
</div>


```javascript
// 5. Export the image

// define an arctic friendly coordinate system
var crs_nplaea = 'PROJCS["Arctic LAEA greenwich",GEOGCS["GCS_WGS_1984",DATUM["D_WGS_1984",SPHEROID["WGS_1984",6378137.0,298.257223563]],PRIMEM["Greenwich",0.0],UNIT["Degree",0.0174532925199433]],PROJECTION["Lambert_Azimuthal_Equal_Area"],PARAMETER["False_Easting",0.0],PARAMETER["False_Northing",0.0],PARAMETER["Central_Meridian",0.0],PARAMETER["Latitude_Of_Origin",90.0],AUTHORITY["EPSG","102017"],UNIT["Meter",1.0]]'

// export image in laea
Export.image(slopes_peak, 'mcd43a4_peak_summer_ndvi_2001_2013_trends', 
       { 
         'scale': 1000,
         'crs': crs_nplaea,
         'region': canada_bounds.geometry(),
         'maxPixels': 10000000000000,
         'driveFolder':'GEE_COURSE'
       });
```

## Discover the GEE API | trends in summer NDVI example {.build .smaller}

<div>
**Bonus:**  
Evaluate MODIS 16 days product according to associated quality flags  

> - filter MODIS NDVI (keep only high quality data)  
> - map indexs to qualify the quality of created images  
    + average number of observation used to calculate a NDVI peak  
    + number of NDVI peaks used to estimate the trend  
</div>

To do that you will roughly need to use the same procedures and tools than the formal scripts.. and the script is [here](https://code.earthengine.google.com/563e86500450d0c58b842e56c3a75771)... maybe we can go throw together. 


# We are done!
