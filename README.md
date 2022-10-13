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

### Launch a Redshift Cluster
I use the aws free trial cluster  with 160gb free storage and a 750 hours uptime per month. The free trial allows for just a single node and a dc2.large node .
![](https://github.com/d-owusu/Million-Songs-Redshift/blob/main/pictures/ksnip_20221012-121724.png)

### Upload to Redshift
Upload the compressed files into redshift by first a creating a schema 
![](https://github.com/d-owusu/Million-Songs-Redshift/blob/main/pictures/ksnip_20221012-132707.png)

Then load the data into redshift.  Note that you have to create a role to allow redshift access to s3 bucket then use the arn from the role created as the credentials in Redshift as seen below
![](https://github.com/d-owusu/Million-Songs-Redshift/blob/main/pictures/ksnip_20221012-132640.png)

### Connect to a BI tool
I connect redshift to tableau to access the data. You have to check the security group associated with Redshift  and permit inbound access on port 5439.

![](https://github.com/d-owusu/Million-Songs-Redshift/blob/main/pictures/ksnip_20221012-174347.png)
