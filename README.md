# Facebook Page Scraper

[![alt text] (https://zenodo.org/badge/19221/yhegde/fb-page-scraper.svg)]
(https://zenodo.org/badge/latestdoi/19221/yhegde/fb-page-scraper)

Facebook Page Scraper is a tool for collecting data from public facebook pages. This tool uses Facebook's Graph API to collect data. Using this tool you can download and archive the data in json files, insert then into MySQL database, and download images

This tool is especially built for keeping it running and collecting large amount of historical, current and future data (posts, comments etc.) from multiple public facebook pages. Check config.properties.template file for various configuration options for running the tool.      

## Quick start guide
* Install MySQL server
 
* Download **config.properties.template** and **fb-data-collector.jar** from [latest release] (https://github.com/yhegde/fb-page-scraper/releases/)

* Rename config.properties.template to **config.properties**, open in a text editor and make relevant changes by following inline instructions

* Start downloading data  
    <pre>java -jar fb-data-collector.jar >> data.log 2>&1 &</pre>

* Download **db.schema.sql** and **fb-inserter.jar** from [latest release] (https://github.com/yhegde/fb-page-scraper/releases/)

* Create facebook database  
     <pre>CREATE DATABASE facebook 
DEFAULT CHARACTER SET utf8 
DEFAULT COLLATE utf8_general_ci;</pre> 

* Create tables in facebook database
     <pre>mysql -u root -pPassword facebook < db.schema.sql</pre>

* Start inserting data into database  
    <pre>java -jar fb-inserter.jar >> insert.log 2>&1 &</pre>

Note: Your config.properties and your *.jar files should be located in the same directory

## License  
Copyright [2015] [Yatish Hegde]

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this software except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
