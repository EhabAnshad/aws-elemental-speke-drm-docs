# AWS Authentication for SPEKE<a name="aws-authentication"></a>

SPEKE requires AWS authentication through IAM roles\. IAM roles are created by the DRM system service or by the operator who owns the DRM endpoint in an AWS account\. Each role is assigned an Amazon Resource Name \(ARN\), which the AWS Elemental product operator provides in the service UI when requesting encryption\. The role’s policy permissions must be configured to give permission to access the key server API and no other AWS resource access\. When the encryptor contacts the DRM key server, it uses the role ARN to assume the role of the key server account holder, which returns temporary credentials for the encryptor to use to access the key server\. 

One common implementation involves the operator or DRM vendor using Amazon API Gateway in front of the key server, and then enabling AWS\_IAM authorization on the API Gateway resource\. You can use the following policy definition example and attach it to a new role to give permissions to the appropriate resource\. In this case the permissions are for all API Gateway resources\. 

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "execute-api:Invoke"
            ],
            "Resource": [
                "arn:aws:execute-api:us-west-2:*:*/*/GET/*"
            ]
        }
    ]
}
```

Finally, a trust relationship is added to the role and the properly named service is selectable by the operator\. 

The following example shows a role ARN that is created for accessing the key server:

```
 
arn:aws:iam::2949266363526:role/DRMKeyServer
```

For more information about the creation of a role, see [AWS AssumeRole](http://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRole.html)\. For more information about signing a request, see [AWS Sigv4](http://docs.aws.amazon.com/general/latest/gr/sigv4_signing.html)\. 