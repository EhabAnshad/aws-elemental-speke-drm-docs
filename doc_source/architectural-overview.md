# Architectural Overview<a name="architectural-overview"></a>

SPEKE can be implemented for any DRM key server\. The following illustration shows a typical architecture using a third\-party key server\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/speke/latest/documentation/)

+ **AWS Elemental Account**—Provides the encryption technology\. The service receives encryption requests from its operator and retrieves the required keys from the DRM key server, through Amazon API Gateway\. It saves the encrypted content to Amazon S3 buckets or Amazon CloudFront\.

+ **Customer AWS Account**—Management of customer trusted roles in the AWS system and DRM key server and proxy communication between the media service and the key server\. Customers enable key server access through IAM role configuration for their account\. API Gateway provides logging capabilities and lets the customer control their relationships with the AWS Elemental service and with the DRM system\. 

+ **DRM Partner Account**—Provides secure keys to the encryptor\. Provides encryption keys to the AWS Elemental services through a SPEKE\-compliant API\. Provides secure licenses to media players for decryption on behalf of viewers\. 

The following illustration shows a typical architecture for a customer\-implemented key server\. In this case, the customer account and partner account are combined\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/speke/latest/documentation/)