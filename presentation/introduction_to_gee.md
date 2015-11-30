---
title: "Introduction to GEE"
author: "Damien g."
date: "10/11/2015"
output:
  ioslides_presentation:
    css: style.css
    incremental: yes
    logo: ~/Work/GEE_COURSE/geecourseshub/materials/figures/AU_GEE_logo_square.png
    smaller: yes
    widescreen: yes
    md_extensions: +hard_line_breaks+footnotes
---

## Important note

A lot of slides, text, images, examples have been **peered from GEE core team folks'** presentations.  

You can find the original documents here:  

[http://earthenginesummit2015.earthoutreach.org/training-materials](http://earthenginesummit2015.earthoutreach.org/training-materials)

<div class="notes">
- Who I am?
    + computer scientist working on ecological problematics
    + french
    + not a teacher
    + not a GEE specialist
    + calf
- Aim of this course
    + make you discover GEE
    + what it is? what you can do with?
    + show you how to be autonome
- 2 parts
    + general introduction
    + practical
- Stop me if too fast, too slow, not clear, break... 
</div>


# Requirements and terms of use

## Terms of use | Who can use GEE?

“... the Services may only be used for **development, evaluation, research, or educational purposes**. Services may be evaluated in a production environment but not for sustained commercial purposes. Maps created with Analysis Capabilities may **not be resold**.”

## Terms of use | Intellectual Property Rights?

“... these Master Terms and the Addendums do not grant either party any express, implied, or other rights to the other’s content or any of the other’s Intellectual Property Rights. Intellectual Property Rights in and to the content accessed through the Services **are the property of the applicable content owner** and may be protected by applicable laws..”

**You own your Intellectual Property Rights and your content**

## Requirements

- have a Google account

- have been accepted as a GEE beta tester 

- have a compatible web browser (Google Chrome, Firefox, ...)

# General presentation of GEE

## What is GEE?

Earth Engine is...

> - Access to over **40 years of Satellite Imagery** (with **daily** updates).

- **Scientific** algorithms to analyze that data (as well as your own data).

- **Google's computer clusters** to analyze the data at scale.

- A web-based tool for interactive data exploration.

- An API for building your own specialized websites.

## What can it do?

<div class="columns-2">
> - get an image

<img src="../materials/figures/GEE_exported_image.png" width=80%>
</div>

## The Earth Engine Public Data Catalog

<img src="../materials/figures/GGE_data_catalogue.png" width=100%>

> - &#62; 200 public datasets
> 
> - &#62; 5 million images
> 
> - &#62; 4000 new images every day
> 
> - &#62; 5 petabytes of data

## What can it do?

<div class="columns-2">
> - get an image
>  
> - **apply an algorithm to an image**

<img src="../materials/figures/GEE_transform_image.png" width=80%>
</div>

## What can it do?

<div class="columns-2">
> - get an image
> 
> - apply an algorithm to an image
> 
> - **filter a collection**

<img src="../materials/figures/GEE_filter_collection.png" height=80%>
</div>

## What can it do?

<div class="columns-2">
> - get an image
> 
> - apply an algorithm to an image
> 
> - filter a collection
> 
> - **map an algorithm over a collection**


<img src="../materials/figures/GEE_transform_collection.png" width=80%>
</div>

## What can it do?

<div class="columns-2">
> - get an image
> 
> - apply an algorithm to an image
> 
> - filter a collection
> 
> - map an algorithm over a collection
> 
> - **reduce a collection**


<img src="../materials/figures/GEE_reduce_collection.png" width=80%>
</div>

## What can it do?

<div class="columns-2">
> - get an image
> 
> - apply an algorithm to an image
> 
> - filter a collection
> 
> - map an algorithm over a collection
> 
> - reduce a collection
> 
> - **compute aggregate statistics**


<img src="../materials/figures/GEE_stats_from_image.png" width=80%>
</div>

## How it works?

<img src="../materials/figures/GEE_processing_1.png" width=65%>

## How it works?

<img src="../materials/figures/GEE_processing_2.png" width=65%>

## How it works?

<img src="../materials/figures/GEE_processing_2b.png" width=65%>

## How it works?

<img src="../materials/figures/GEE_processing_3.png" width=65%>

## How it works?

<img src="../materials/figures/GEE_processing_4.png" width=65%>

## How it works?

<img src="../materials/figures/GEE_processing_5.png" width=65%>

# Main GEE feartures

## The Earth Engine Home Page | [https://earthengine.google.org/](https://earthengine.google.org/)

<div class="columns-2">
> - Browse the **data catalogue**
> - Do some **simple visualisation**
> - Perform simple operations **without having to write any code**


<img src="../materials/figures/GEE_Screenshot_1.png" width=100%>
</div>

## The Earth Engine “Playground” | [https://ee-api.appspot.com/](https://ee-api.appspot.com/)

<div class="columns-2">
> - A web app that combines a **script editor** with a map to **display the results**.
> 
> - Lets you interactively **develop an analysis** workflow using the **Earth Engine JavaScript library**.
> 
> - Includes **example code** to get you started, **reference docs** for library functions, an **output console** 
    and **data inspectors**, a **charting interface**, and data export tools.


<img src="../materials/figures/GEE_Screenshot_2.png" width=100%>
</div>

## The Earth Engine “Playground” | [https://ee-api.appspot.com/](https://ee-api.appspot.com/) {.centered}

<img src="../materials/figures/GEE_Screenshot_3.png" width=85%>

## The Earth Engine Help Page and Help Group
<div class="columns-2">
[https://groups.google.com/forum/?fromgroups&#35;!forum/google-earth-engine-developers](https://groups.google.com/forum/?fromgroups&#35;!forum/google-earth-engine-developers)
<br></br>
<img src="../materials/figures/GEE_Screenshot_4.png" width=100%>
<br></br> 
[https://developers.google.com/earth-engine/](https://developers.google.com/earth-engine/)
<br></br>
<img src="../materials/figures/GEE_Screenshot_5.png" width=100%>
</div>



