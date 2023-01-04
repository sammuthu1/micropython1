---
title: Transforming PII/PHI in data files
author: J. E. Tannenbaum
author_url: https://github.optum.com/jtannenb
author_image_url: https://github.optum.com/jtannenb.png
tags: [Tech Talks]
hide_table_of_contents: false
---
One of the issues we all face when working with test teams is how to make sure the data that used in a test is realistic, but not readily identifiable.  In the past, our test teams would take data files from our production system, manually change some parameters, and then use it for a specific test case.  The process was time intensive as well as inconsistent.  Each tester had their own "secret sauce" for transforming the data, making it difficult to share test data between teams and systems.  We worked with the TDSaaS team under Debra Navarro to transform our databases and our commonly used file formats (837, COB2, UFE) via a service catalog request.  That worked well for the well-defined databases and files, but still left us with a problem when we looked at other files that needed to be transformed before entering our non-production systems.

As we progressed with our testing, we found that one system, in particular, had data files from multiple sources.  Each file had its own data structures, as well as contained different sets of data.  Their import process was built around custom import functions to read the data into a standardized database.  The database was easily handled through our normal process.  The initial attempt to transform the data was to continue to write specific intake functions, similar to the work that was done for the commonly used files.  This approach quickly became untenable, as the number of file formats continued to grow.  The solution needed to be flexible and extensible.  Today's file might be tab-delimited and tomorrow's file might be in a fixed format.  Even the field delimiters can change from file to file.  Additionally, some files would contain name data in the form of the first name followed by the last name, some would add a middle initial, and some would have names where the last name was followed by the first name.

The solution evolved as the number of files grew.   We needed to create a process that took the non-standard file formats and converted them into a standard file format that the service catalog function could digest.  The process also needed to be easily configurable and understandable for non-technical users.  Fortunately, each data file came with a data dictionary, defining the file format.  The data dictionaries were analyzed and a method was constructed such that a simple configuration file could be created to accompany the data file for intake into the service catalog request.  

As an example, if the file format contained data in the following format:

Firstname,Lastname,Address,City,State,Zipcode,ICD-10 code

We could create a configuration file as follows:
```
COMMA
1,FirstName
2,LastName
3,AddressLine1
4,City
6,ZipCode

```
Note that we did not need to transform the state, nor did we change the ICD-10 code included in the file.  The process would then deconstruct the file and tag each element to be transformed.  The intermediate XML file would look like this:
```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<RawData filename="inputFileName.txt" type="ConfigFileName.dat">
<Record idx="1">
<Data idx="1" type="FirstName">Bob</Data>
<Data idx="2" type="LastName">Jones</Data>
<Data idx="3" type="AddressLine1">123 Main Street</Data>
<Data idx="4" idx2="6" type="CityZip">Our Town,12345</Data>
</Record>
.
.
.

```
The transformation process was updated such that it would decompose the input file according to the configuration file, transform the resultant XML file, then re-assemble the output file with the de-identified data in place of the PII/PHI data that was previously tagged.

The service is currently live.  It can be found by logging into the service catalog https://servicecatalog.uhc.com/sc/home.aspx, searching for UFE (Unified Front End), selecting MRIS - Distributed as the Application and Generic_File_Masking as the Application/File.  A requester has to be a member of “Eligibility_and_Claim_File_Masking” AD group to access the file folders where the files are stored for processing.  Complete details on the service and the different options for configuration files can be found here: https://uhgazure.sharepoint.com/:p:/r/sites/TDSaaS/Training%20Material/File%20Masking/Generic_File_Masking_Automation_User_Guide.pptx?d=w3a78283ccc7d405f8fd0501015b3de17&csf=1&web=1&e=xveimw