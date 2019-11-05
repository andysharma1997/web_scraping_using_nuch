# Web_scraping_using_nuch and integration with solr
This is a description of how to install nuch and configure it and use solr with nuch for searching 
# Install Nutch
Download a binary package (apache-nutch-1.X-bin.zip) from http://mirrors.estointernet.in/apache/nutch/1.16/

Unzip your binary Nutch package using unzip apache-nutch-1.X-bin.zip

export this path to environment usig export NUTCH_RUNTIME_HOME="path/to/apache-nutch-1.X" 
#  Verify your Nutch installation
cd apache-nutch-1.X
./bin/nutch must return 

Usage: nutch COMMAND where command is one of:

readdb            read / dump crawl db

mergedb           merge crawldb-s, with optional filtering

readlinkdb        read / dump link db

inject            inject new urls into the database

generate          generate new segments to fetch from crawl db

freegen           generate new segments to fetch from text files

fetch             fetch a segment's pages

...

#  Some troubleshooting tips:
Run the following command if you are seeing "Permission denied":

 chmod +x bin/nutch
 
Setup JAVA_HOME if you are seeing JAVA_HOME not set

export JAVA_HOME=$(readlink -f /usr/bin/java | sed "s:bin/java::")

#  Crawl your first website
1.Customize your crawl properties, where at a minimum, you provide a name for your crawler for external servers to recognize

2.Set a seed list of URLs to crawl

# Customize your crawl properties
add the following configurations to the  conf/nutch-site.xml file
```
<property>
 <name>http.agent.name</name>
 <value>My Nutch Spider</value>
</property>
```
## Create a URL seed list

