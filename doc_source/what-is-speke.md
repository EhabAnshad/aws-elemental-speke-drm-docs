# What Is Secure Packager and Encoder Key Exchange?<a name="what-is-speke"></a>

Secure Packager and Encoder Key Exchange \(SPEKE\) defines the standard for communication between AWS Elemental encoding and packaging offerings and digital rights management \(DRM\) system key servers\. AWS Elemental MediaConvert uses SPEKE to encrypt video on demand \(VOD\)\. AWS Elemental MediaPackage and AWS Elemental Live use SPEKE to encrypt live content\. 

**Topics**
+ [General Architecture](#general-architecture)
+ [AWS Elemental Media Services Architecture](#services-architecture)
+ [How to Get Started](#how-to-start)

## General Architecture<a name="general-architecture"></a>

The following illustration shows a high\-level view of the SPEKE content encryption architecture\.

![\[The encryptor receives encryption requests from the person operating it. The encryptor sends a request to the DRM system key server for keys that it can use to secure the encrypted content. It sends the encrypted content to a player. The player requests keys from the same DRM system key server, which the player uses to unlock the content and serve it to its viewers.\]](http://docs.aws.amazon.com/speke/latest/documentation/images/speke-high-level.png)

These are the main components of the preceding architecture:
+ **Encryptor** – Receives encryption requests from its operator, and retrieves the required keys from the DRM key server to secure the encrypted content\. 
+ **DRM system key server** – Provides encryption keys to the encryptor through a SPEKE\-compliant API\. Provides licenses to media players for decryption\. 

## AWS Elemental Media Services Architecture<a name="services-architecture"></a>

The following illustration shows the high\-level architecture when SPEKE is used with the AWS Elemental Media Services\.

![\[The AWS Elemental media service, Amazon API Gateway, AWS IAM, and AWS Certificate Manager all reside in the same AWS Region. The AWS operators configure API Gateway and IAM to provide a proxy between the media service and the DRM system key server. The AWS operators optionally configure certificates in the certificate manager for use by the media service for content key encryption. The media service receives encryption requests from its operators. The media service sends a request through API Gateway to the DRM system key server for keys that the media service can use to secure the encrypted content. If it is configured with certificates, the media service communicates with the certificate manager to manage content key encryption. The media service sends the encrypted content to an Amazon S3 bucket or to Amazon CloudFront. When a viewer asks to see the content on a player, the player requests the encrypted content from Amazon S3 or Amazon CloudFront and requests keys from the same DRM system key server. The player uses the keys to unlock the content and serve it to its viewers.\]](http://docs.aws.amazon.com/speke/latest/documentation/images/speke-services-high-level.png)

These are the main services and components:
+ **AWS Elemental Media Service** – Provides the encryption technology\. The service receives encryption requests from its operator and retrieves the required keys from the DRM key server, through Amazon API Gateway\. It delivers the encrypted content to an Amazon S3 bucket or through an Amazon CloudFront distribution\. You must instantiate the AWS Elemental Media Service and the API that you create with API Gateway in the same AWS Region\. 
+ **AWS IAM and Amazon API Gateway** – Manages customer\-trusted roles and proxy communication between the media service and the key server\. API Gateway provides logging capabilities and lets customers control their relationships with the AWS Elemental Media Service and with the DRM system\. Customers enable key server access through IAM role configuration\. The API Gateway API must reside in the same AWS Region as the AWS Elemental Media Service\. 
+ **AWS Certificate Manager** – \(Optional\) Provides certificate management for content key encryption\. Encrypting content keys is the recommended practice for secure communication\. The certificate manager must reside in the same AWS Region as the AWS Elemental Media Service\.
+ **DRM system key server** – Provides encryption keys to the AWS Elemental Media Services through a SPEKE\-compliant API\. Also provides licenses to media players for decryption\. 

## How to Get Started<a name="how-to-start"></a>

**Are you a customer?**  
Partner with an AWS Elemental DRM solution provider to get set up to use encryption\. For details, see [Customer Onboarding](customer-onboarding.md)\.

**Are you a DRM solution provider or a customer with your own key server?**  
Expose a REST API for your key server in compliance with our AWS Elemental SPEKE specification\. For details, see [SPEKE API Specification for DRM Solution Providers](speke-api-specification.md)\.