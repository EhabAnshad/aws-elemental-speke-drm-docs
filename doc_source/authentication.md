# Authentication<a name="authentication"></a>

SPEKE requires authentication for use with AWS Elemental products and services\.

**Topics**
+ [Authentication with AWS Services](#aws-authentication)
+ [Authentication with AWS Elemental Products](#authentication-on-prem)

## Authentication with AWS Services<a name="aws-authentication"></a>

SPEKE requires AWS authentication through IAM roles for use with AWS Elemental Media Services\. IAM roles are created by the DRM system service or by the operator who owns the DRM endpoint in an AWS account\. Each role is assigned an Amazon Resource Name \(ARN\), which the AWS Elemental service operator provides on the service console when requesting encryption\. The role’s policy permissions must be configured to give permission to access the key server API and no other AWS resource access\. When the encryptor contacts the DRM key server, it uses the role ARN to assume the role of the key server account holder, which returns temporary credentials for the encryptor to use to access the key server\. 

One common implementation involves the operator or DRM vendor using Amazon API Gateway in front of the key server, and then enabling AWS IAM authorization on the API Gateway resource\. You can use the following policy definition example and attach it to a new role to give permissions to the appropriate resource\. In this case, the permissions are for all API Gateway resources\. 

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

Finally, the role requires the addition of a trust relationship, and the operator must be able to select the service\. 

The following example shows a role ARN that is created for accessing the key server:

```
 
arn:aws:iam::2949266363526:role/DRMKeyServer
```

For more information about the creation of a role, see [AWS AssumeRole](https://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRole.html)\. For more information about signing a request, see [AWS Sigv4](https://docs.aws.amazon.com/general/latest/gr/sigv4_signing.html)\. 

## Authentication with AWS Elemental Products<a name="authentication-on-prem"></a>

For AWS Elemental Live 2\.13\.3, the media encoder and key server handle authentication using a secure web address and a user name and password\. 

AWS Elemental Live uses SSL/TLS and basic or digest authentication to secure communication with the DRM solution provider\. We recommend that you use digest for the added security, but at a minimum you should use basic authentication over HTTPS\. 

Both types of authentication use the `Authorization` header in the HTTP request: 
+ **Digest authentication** – The authorization header consists of the identifier `Digest` followed by a series of values that authenticate the request\. Specifically, a response value is generated through a series of MD5 hash functions that include a unique, one\-time\-use nonce from the server that is used to ensure that the password travels securely\. 
+ **Basic authentication** – The authorization header consists of the identifier `Basic` followed by a base\-64 encoded string that represents the user name and password, separated by a colon\. 

For information about basic and digest authentication, including detailed information about the header, see the Internet Engineering Task Force \(IETF\) specification [RFC 2617 \- HTTP Authentication: Basic and Digest Access Authentication](https://tools.ietf.org/html/rfc2617)\.