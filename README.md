# Million-Songs-Redshift
 Extracting data from a database of one million music tracks and load them into AWS Redshift  through S3 

### Getting the Metadata
wget c http://labrosa.ee.columbia.edu/millionsong/sites/default/files/AdditionalFiles/track_metadata.db'

### Loading data into Redshift

I break the  million row file into separate files and compress them to the loading into redshift easier ![](https://github.com/d-owusu/Million-Songs-Redshift/blob/main/pictures/ksnip_20221013-102407.png)
