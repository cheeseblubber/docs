# How to download and dump wikipedia into a postgres db

* Download the file through [torrent](https://meta.wikimedia.org/wiki/Data_dump_torrents#enwiki)
* Unzip the download with `bzip2 -v -d enwiki-20150602-pages-articles.xml.bz2`
* Download [java utility](https://meta.wikimedia.org/wiki/Data_dumps/mwdumper) to convert xml to sql
* convert xml to sql file with `java -jar mwdumper.jar --format=sql:1.5 ~/filepath_to_extracted_file`
* Download [table schema](https://github.com/wikimedia/mediawiki/blob/master/maintenance/postgres/tables.sql) 
  for the version of database you are using
* Create database with in postgres with `create database wikidump`
* Import data with `psql -d wikidump -f ~/path_to_extract_sql_file`
