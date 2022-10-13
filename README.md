# Million-Songs-Redshift
 Extracting data from a database of one million music tracks and load them into AWS Redshift  through S3 

### Getting the Metadata
wget c http://labrosa.ee.columbia.edu/millionsong/sites/default/files/AdditionalFiles/track_metadata.db'

### Loading data into Redshift

I break the  million row file into separate files and compress them to the loading into redshift easier ![](https://github.com/d-owusu/Million-Songs-Redshift/blob/main/pictures/ksnip_20221013-102407.png)


### S3 Bucket
Create your s3 bucket and uyour redshift use the same region where redshift cluster will be located

### Upload files
Load files into your created s3 bucket
![](https://github.com/d-owusu/Million-Songs-Redshift/blob/main/pictures/ksnip_20221012-104051.png)

### Manifest
I create a manifest of the files to upload. The file should also be uploaded into the same s3 bucket

![](https://github.com/d-owusu/Million-Songs-Redshift/blob/main/pictures/ksnip_20221013-121659.png)
