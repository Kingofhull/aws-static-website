# aws-static-website
## My first project as a DevOps engineer 
### Below are the steps to take in other to carry out this project and also i will be attaching some pecture evidence
1. create an S3 bucket, the following steps will guide you
- click on create bucket
- input your bucket name (domain)
- unblock all public access
- disable bucket versioning
- enable bucket key
- in object ownership (choose ACLs disabled)
- then click on create bucket
2. Click on the bucket you just created to open it
- go to permision and generate bucket policy
- go to property
- click on edit static website hosting and enable websit hosting
- tick the "host a static website" option
- in the index document type "index.html"
- Error document is optional, you can leave it or type "error.html" and save changes
3. go to route 53
- click on create hosted zone
- input your domain name
- description is optional
- make hosted zone public
- click on create hosted zone
- go to the website where you purchased your domain and carry out the necessary configuration
- click on update and allow it to update
4. Next is to create a certificate manager
- go to certificate manager and click on request
- tick "request a public certificate" and click next
- input your domain name
- in Validation method, choose DNS as it's faster
- click on requet
- copy out CNAME Name and CNAME value
5. now you have to create a record set and to do that:
- go baack to Route 53 and click on hosted zone
- click on the domain name you are working on in the hosted zone
- click on create record
- select CNAME record
- paste the CNAME Name and record you copied respectively
- click o create record
6. go to cloud front and click on create distribution
- go back to your S3 bucket and copy the url and paste, removing the http//
- tick "redirect http to https
- choose the certificate you got
- click create distribution and copy the url and test if it's working
7. Finally go back to route 53 and click on create record
- at the record type, select "A-Route trafic......."
- tick on Alias to put it on
- select "Alis to cloudfront distribution"
- choose the distribution you have created and click on create record.
#### this will see your static website with your domain name working.

![Screenshot (5)](https://github.com/Kingofhull/aws-static-website/assets/135378776/c9fa8138-18a0-4ab8-b02b-fc2f8aa84d3b)

