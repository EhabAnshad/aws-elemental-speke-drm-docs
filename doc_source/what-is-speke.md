# What Is AWS Elemental Secure Packager and Encoder Key Exchange?<a name="what-is-speke"></a>

AWS Elemental Secure Packager and Encoder Key Exchange \(SPEKE\) is part of the AWS Elemental content encryption protection strategy for media services customers\. SPEKE defines the standard for communication between our media services and digital rights management \(DRM\) system key servers\. SPEKE is used to encrypt video on demand \(VOD\) content through AWS Elemental MediaConvert and for live content through AWS Elemental MediaPackage\. 

The following illustration shows a high\-level view of the AWS Elemental content encryption architecture\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/speke/latest/documentation/)

These are the main services and components:

+ **AWS Elemental media service**—Provides the encryption technology\. The service receives encryption requests from its operator and retrieves the required keys from the DRM key server, through Amazon API Gateway\. It delivers the encrypted content to Amazon S3 buckets or Amazon CloudFront\.

+ **AWS IAM and API Gateway**—Manages customer trusted roles and proxy communication between the media service and the key server\. API Gateway provides logging capabilities and lets customers control their relationships with the AWS Elemental media service and with the DRM system\. Customers enable key server access through IAM role configuration\. 

+ **DRM system key server**—Provides encryption keys to the AWS Elemental media services through a SPEKE\-compliant API\. Also provides licenses to media players for decryption\. 

## How to Get Started<a name="how-to-start"></a>

**Are you a customer?**  
Partner with an AWS Elemental DRM solution provider to get set up to use encryption\. For details, see [[ERROR] BAD/MISSING LINK TEXT](customer-onboarding.md)\.

**Are you a DRM solution provider or a customer with your own key server?**  
Expose a REST API for your key server in compliance with our AWS Elemental SPEKE specification\. For details, see [[ERROR] BAD/MISSING LINK TEXT](speke-api-specification.md)\.