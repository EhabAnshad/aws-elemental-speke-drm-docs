# Are You New to SPEKE?<a name="are-you-new-to-speke"></a>

This section lists some basic terminology related to SPEKE and AWS Elemental encoding implementations of SPEKE\. The section also provides links to related specifications and AWS services\.

## Related Services and Specifications<a name="related-services-and-specifications"></a>
+ [API Gateway Permissions](https://docs.aws.amazon.com/apigateway/latest/developerguide/permissions.html) – How to control access to an API with AWS Identity and Access Management \(AWS IAM\) permissions\.
+ [AWS AssumeRole](https://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRole.html) – How to use AWS Security Token Service \(AWS STS\) to assume role functionality\.
+ [AWS Sigv4](https://docs.aws.amazon.com/general/latest/gr/sigv4_signing.html) – How to sign an HTTP request using Signature Version 4\. 
+ [DASH\-IF CPIX specification](https://dashif.org/docs/DASH-IF-CPIX-v2-0.pdf) – The DASH\-IF Content Protection Information Exchange Format \(CPIX\) specification, which this SPEKE specification is based on\. 
+ [DASH\-IF System IDs](https://dashif.org/identifiers/content_protection/) – The list of registered system IDs for DRM key providers\.
+ [https://github.com/awslabs/speke-reference-server](https://github.com/awslabs/speke-reference-server) – Example reference key server to use with your AWS account, to help you get started with a SPEKE implementation in AWS\.

## Terminology<a name="terminology"></a>
+ **ARN** – Amazon Resource Name\. Uniquely identifies an AWS resource\. 
+ **Content key** – Cryptographic key used for encrypting part of the content\.
+ **Content provider** – Publisher who provides the rights and rules for delivering protected media\. The content provider might also provide source media \(mezzanine format, for transcoding\), asset identifiers, key identifiers \(KIDs\), key values, encoding instructions, and content description metadata\.
+ **Encryptor** – Video processing component \(encoder, packager, or transcoder\)\. For example, AWS Elemental MediaConvert, AWS Elemental MediaPackage, and AWS Elemental Live\.
+ **Key server** – Component of a DRM system that is used to provide keys to the encryptor\.
+ **Operator** – Person in charge of operating the overall system, including the encryptor and the DRM system\.
+ **Player** – Media player operating on behalf of a viewer\. Gets its information from different sources, including the media manifest files, media files, and DRM licenses\. Requests licenses from the DRM server on behalf of the viewers\.