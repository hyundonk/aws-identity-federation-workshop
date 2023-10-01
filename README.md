# aws-identity-federation-workshop
AWS Identity Federation with Active Directory Demo

Notes on exercising below workshop
https://identity-federation.awssecworkshops.com/microsoft/build/

### Task1. Deploying ADFS-Master-Template.yaml

- python3.6 is deprecated in Lambda. Replace with python3.9
- Issue with populating VPC, PublicSubnetId, KeyName parameters. Set default values for those.
- AMI ami-0382724d79a997027 (Windows 2012 R2) is deprecated. Used ami-01fba1be50c79002e instead.


### Task5. Importing SSL certificate for ADFS

- 'idp1cert.pfx' certificate which is provided on ADFS EC2 Instance is expired. Created one instead using instructions in the link below.
https://www.lesstif.com/system-admin/openssl-root-ca-ssl-6979614.html
https://stackoverflow.com/questions/69343254/the-password-you-entered-is-incorrect-when-importing-pfx-files-to-windows-cer

```
# used '-nomac' option as below. Otherwise, got 'password incorrect' error
openssl pkcs12 -export -certpbe PBE-SHA1-3DES -keypbe PBE-SHA1-3DES -nomac -inkey lesstif.com.key -in lesstif.com.crt -out lesstif.com2.pfx -certfile lesstif-rootca.crt
```



