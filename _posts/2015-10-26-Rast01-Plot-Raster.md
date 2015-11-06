---
layout: post
title: "Lesson 01: Plot Rasters in R"
date:   2015-10-28
authors: [Jason Williams, Jeff Hollister, Kristina Riemer, Mike Smorul, Zack Brym]
dateCreated:  2015-10-23
lastModified: 2015-10-23
category: spatio-temporal-workshop
tags: [module-1]
mainTag: GIS-Spatial-Data
description: "This post explains the simple plotting function in the `raster` package."
code1: 
image:
  feature: NEONCarpentryHeader_2.png
  credit: A collaboration between the National Ecological Observatory Network (NEON) and Data Carpentry
  creditlink: http://www.neoninc.org
permalink: /R/Plot-Rasters-In-R.R
comments: false
---

{% include _toc.html %}

##About
This post explains the simple plotting function in the `raster` package.

**R Skill Level:** Intermediate - you've got the basics of `R` down.

<div id="objectives" markdown="1">

###Goals / Objectives

After completing this activity, you will know:

* what a raster band is
* how to plot a single band raster in R

###Things You'll Need To Complete This Lesson


###R Libraries to Install:

* **raster:** `install.packages("raster")`
* **rgdal:** `install.packages("rgdal")`

####Tools To Install

Please be sure you have the most current version of `R` and preferably
R studio to write your code.


####Data to Download

Download the workshop data:

* <a href="http://figshare.com/articles/NEON_AOP_Hyperspectral_Teaching_Dataset_SJER_and_Harvard_forest/1580086" class="btn btn-success"> DOWNLOAD Sample NEON LiDAR data in Raster Format & Vegetation Sampling Data</a><


The LiDAR and imagery data used to create the rasters in this dataset were 
collected over the Harvard and San Joaquin field sites 
and processed at <a href="http://www.neoninc.org" target="_blank" >NEON </a> 
headquarters. The entire dataset can be accessed by request from the NEON website.

####Recommended Pre-Lesson Reading

* <a href="http://cran.r-project.org/web/packages/raster/raster.pdf" target="_blank">
Read more about the `raster` package in R.</a>

</div>


    # Plot raster file and change some parameters
    plot(DSM) #Necessary to explicitly differentiate between base plot and raster plot?

![ ]({{ site.baseurl }}/images/rfigs/01-Plot-Raster/pseudo-code-1.png) 

    pixels <- ncol(DSM) * nrow(DSM)
    hist(DSM, col = "blue", maxpixels = pixels)

![ ]({{ site.baseurl }}/images/rfigs/01-Plot-Raster/pseudo-code-2.png) 

    myCol <- terrain.colors(10)
    plot(DSM, breaks = c(320, 340, 360, 380, 400), col = myCol, maxpixels = pixels) #optional argument

![ ]({{ site.baseurl }}/images/rfigs/01-Plot-Raster/pseudo-code-3.png) 

    plot(DSM, zlim = c(340, 400)) #optional argument

![ ]({{ site.baseurl }}/images/rfigs/01-Plot-Raster/pseudo-code-4.png) 

    #`image` v. `plot`
    # TODO: challenge


    # Code here