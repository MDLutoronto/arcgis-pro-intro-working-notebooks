---
title: "Introduction to Working with Notebooks in ArcGIS Pro"
layout: "home"
description: "This guide provides some introductory information on how to use notebooks in the ArcGIS Pro environment. You will learn about what notebooks are, how to use them, and some useful tips on using ArcPy to analyze your geospatial data."
created_date: 2025-02-18
permalink: "/"  #! Remove this if not the homepage
maintainer:
 - name: Cole White
   link: https://library.utoronto.ca/staff/cole-white
---

# Introduction to Working with Notebooks in ArcGIS Pro

This guide provides some introductory information on how to use notebooks in the ArcGIS Pro environment. You will learn about what notebooks are, how to use them, and some useful tips on using ArcPy to analyze your geospatial data.

**Getting Started with ArcGIS Pro Notebooks**

ArcGIS Pro notebooks provide users with an interactive environment for running Python code, automating workflows, and conducting geospatial analysis. They combine the power of Python with the spatial capabilities of ArcGIS Pro to help you streamline tasks and visualize data seamlessly. This guide will walk you through the basics of how to get started with notebooks in ArcGIS Pro.

The Map & Data Library has some sample ArcGIS Pro notebooks available [here](https://github.com/MDLutoronto/ArcGISPro-Notebooks). We also have other workshops on Python through Jupyter. Please feel free to explore our [previous Python workshops](https://mdl.library.utoronto.ca/technology/tutorials/python-information-tutorials-and-workshops) and tutorials if you are looking to learn more.

**Working with Notebooks**

Notebooks are a Python-based program file that users can interact with. It is a document-style workspace that allows you to combine code, output, and visualize data in a single environment. Work is conducted in a file type called *.ipynb*. These are “interactive Python notebook” files that are formatted into a notebook structure. Python code can be run in blocks or cells directly within ArcGIS Pro, which reduces the siloed workflow between traditional Jupyter Notebooks and desktop GIS software.

Typically, notebooks are run through [Jupyter](https://jupyter.org/), an open-source interface for manipulating notebooks. UofT also hosts a web-based platform for [JupyterHub](https://datatools.utoronto.ca/).

**Creating a Notebook in ArcGIS Pro**

1. With your ArcGIS Pro open, navigate to a new or an existing project.

    1. Notebooks are nested within your projects, so be sure to select the correct project environment for where you want to create your notebook.
2. Create a New Notebook.

    1. There are multiple methods of creating a notebook:

        1. Click the *Insert* tab on the top ribbon, and click the *New Notebook* button.  
            <img src='{{ '/assets/images/image_29.png' | relative_url }}' alt='Creating a Notebook using the Insert Tab' title='' width='561' height='202' />
        2. Another method is going to the *Analysis* tab, and going to Python, where you can open a new notebook.  
            <img src='{{ '/assets/images/image_30.png' | relative_url }}' alt='Creating a Notebook using the Analysis Tab' title='' width='552' height='323' />
        3. Or you can access the *Catalog* pane, and navigate your project directory (project geodatabase) where you can right click and select *New > Notebook*. Notice that once you add a notebook, a new folder will be created storing all your notebooks.  
            <img src='{{ '/assets/images/image_31.png' | relative_url }}' alt='Creating a Notebook using the Catalog Pane' title='' width='419' height='492' />
    2. Notebooks open in your view and can be snapped to a particular region by holding the tab. It will start as an empty file with a blank cell, where you can begin writing your Python code.

**Opening an Existing Notebook**

1. Existing Notebooks can be opened through your project *Catalog* pane.
2. Browse to the Notebooks folder within your project.

    1. Right click the notebook you identified and select *Open.*
3. If you would like to add a notebook from a file that has been shared with you / a file in another folder, you can do this by clicking the *Insert* tab on the ribbon, and click the *Add and Open Notebook* button (similar to Step 2ai). This will open your file explorer, allowing you to browse the directory in which the notebook file is located.
4. Sometimes, you may be provided with an ArcGIS Project file (with a .aprx file indicator). Opening this will also allow you to access any attached notebooks that were previously embedded within the project.

**How to Execute Code in a Notebook**

1. Write your code:

    1. In a notebook cell, type your Python code using standard syntax (e.g., importing libraries, defining variables, running functions).
    2. Cells can be initialized as code, markdown, or raw.

        1. Code cells are what you would use to input Python language. These types of cells are denoted by [ ].
        2. Markdown cells are what you would use to format text using the markdown language. Options like bolding or italicizing are available to you in these cells. Elements like images, videos, or other explanatory content are also formattable here.
        3. Raw cells are not executed by the notebook. They will be passed over when running.
2. Run the Code:

    1. To execute the code in a cell, press *Shift + Enter* or *Control/Command + Enter*, or you can use the *Run* button within the notebook toolbar.
    2. The output of the code (such as calculations, tables, visualizations, etc.) will appear directly below the cell in which you ran.  
        <img src='{{ '/assets/images/image_35.png' | relative_url }}' alt='Executing Code using the Run button' title='' width='676' height='160' />
3. Running the Entire Notebook

    1. If you'd like to execute all cells at once, you can use the *Run All* option found in the *Command Palette* menu dropdown.  
    <img src='{{ '/assets/images/image_36.png' | relative_url }}' alt='Accessing the Command Palette menu' title='' width='682' height='167' />
    2. The *Command Palette* contains many functions useful to users, such as duplicating cells or merging code together. One of the first functions you may need will be the *Insert Cells*, which allows you to add additional cells in your notebook. FYI – many of these functions have keyboard shortcuts, which you can identify within the Command Palette.

**Saving and Sharing Notebooks**

Saving a Notebook

Saving your work can be done by clicking *Save* or *Control + S*. As previously mentioned, your work will be saved as an *.ipynb* file. Note: when saving a file, it captures the notebook in its current state, meaning outputs will be saved at their current version. You can always clear all outputs or run the entire notebook for an updated file save.

Sharing a Notebook

You can share your notebook by exporting it or providing access to the notebook file. Notebooks are saved in the same file directory as your ArcGIS Project. If you're working in a shared project, team members can access the same notebook.

**Getting Started with ArcPy**

[ArcPy](https://www.esri.com/en-us/arcgis/products/arcgis-python-libraries/libraries/arcpy) is a Python library/package created by GIS users that enables geospatial analysis, data processing, and workflow automation. Note that ArcPy is a package that is part of the default Python distribution within ArcGIS Pro. If ArcGIS Pro is not installed and licensed, ArcPy functions will not execute.

Here are some starters for ArcPy in notebooks using ArcGIS Pro:

* Be sure to add your layers to the map view if you want to see changes parallel to your code.

    + Layers not presently in the active map view can be refenced by using the file path.   
    + There are different ways to add your data from the file path:     
    	- *r"C:\Tutorials\NotebooksArcPro\Test.gdb\shapefile"*  
    	- *"C:/Tutorials/NotebooksArcPro/Test.gdb/shapefile"*   
    	- *"C:\\Tutorials\\NotebooksArcPro\\Test.gdb\\shapefile"*   
* You can set your working environment/directory by running this line of code

    + *"arcpy.env.workspace = "Your Environment"*   
    + Remember to use one of the specific encoding methods above.
* Geoprocessing tools parameters and additional documentation are always viewable alongside regular usage on the ArcGIS webpage.

    + Here is an example of the [Buffer Tool](https://pro.arcgis.com/en/pro-app/latest/tool-reference/analysis/buffer.htm), where the ArcPy tool is available with required and optional parameters listed.  
        <img src='{{ '/assets/images/image_37.png' | relative_url }}' alt='ArcGIS Pro documentation for Buffer tool' title='' width='470' height='430' />
* Verify if you want to enable features to be overwritten. This can be changed by running this line of code to modify the environment settings: *arcpy.env.overwriteOutput = True*.

**Tips and Best Practices**

Below are a few pointers on guidelines for working in Notebooks through ArcGIS Pro. As with any project (especially with programming), things can get messy and unorganized. There are tools and practices users can adopt to streamline their work.

* Using Python libraries:
	+ ArcGIS Pro notebooks supports standard Python libraries such as *pandas, geopandas, numpy, and matplotlib* as well as the ArcGIS suite of geoprocessing tools like *arcpy*.
	+ Libraries offer functions that simplify coding actions.
	+ You can add these to your project by importing them ex. [import pandas as pd]
* Organize Code with Cells:
	+ You can split your code into multiple cells for better organization and easier debugging.
* Comment, Comment, Comment
	+ Commenting is a powerful yet often overlooked practice in coding projects.
	+ They help to communicate what blocks of code do to others and yourself.
	+ You can create a comment using the # symbol before your code begins.
* Visualize Results:
	+ Notebooks allow you to display visualizations like maps and charts in line with your code, which can help you better understand you data as you work.
	+ For example, if you wanted to look at the data distribution of your data before deciding upon a classification scheme, you can create a histogram.

**Additional Resources and Further Reading**

Wondering if Notebooks and Python is for you? Here are some more resources about how you can implement and use notebooks for your work.

* Esri Lesson | [Getting Started with Notebooks in ArcGIS Pro](https://learn.arcgis.com/en/projects/get-started-with-notebooks-in-arcgis-pro/)
* Esri Tutorials | [Learn Python with ArcGIS Notebooks](https://learn.arcgis.com/en/paths/learn-python-with-arcgis-notebooks/)
* Esri Academy | [ArcGIS Notebooks Basics](https://www.esri.com/training/catalog/5fd024722831fd696d26d53b/arcgis-notebooks-basics/)
* Esri Documentation | [What is ArcPy?](https://pro.arcgis.com/en/pro-app/latest/arcpy/get-started/what-is-arcpy-.htm)
* ArcGIS Blog | [Introducing ArcGIS Notebooks in ArcGIS Pro](https://www.esri.com/arcgis-blog/products/arcgis-pro/analytics/introducing-arcgis-notebooks-in-arcgis-pro/)
* [FAQ for ArcGIS Notebooks](https://community.esri.com/t5/python-documents/arcgis-notebooks-in-arcgis-pro-3-1-faq/ta-p/1261606)
* [Examples of ArcGIS Notebooks](https://doc.arcgis.com/en/arcgis-online/get-started/about-sample-notebooks.htm)
* Map and Data Library sample ArcGIS Notebooks | [https://github.com/MDLutoronto/ArcGISPro-Notebooks](https://github.com/MDLutoronto/ArcGISPro-Notebooks)
