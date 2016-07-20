Move Objects in one bucket to another bucket

1. Configure the AWS credential

aws configure


2. Sync

aws s3 sync s3://source-bucket/source-folder s3://destination-bucket/destination-folder

