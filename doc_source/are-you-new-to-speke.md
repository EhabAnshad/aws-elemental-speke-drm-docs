# Are You New to SPEKE?<a name="are-you-new-to-speke"></a>

This section lists some basic terminology related to SPEKE and AWS Elemental encoding implementations of SPEKE and provides links to related specifications and AWS services\.

## Terminology<a name="terminology"></a>
+ **ARN** – Amazon Resource Name\. Uniquely identifies an AWS resource\. 
+ **Content Key** – Cryptographic key used for encrypting part of the content\.
+ **Content Provider** – Publisher who provides the rights and rules for delivering protected media\. The content provider might also provide source media \(mezzanine format, for transcoding\), asset identifiers, key identifiers \(KIDs\), key values, encoding instructions, and content description metadata\.
+ **Encryptor** – Video processing component \(a packaging stage as part of a compressor or packager\)\. For example, AWS Elemental MediaConvert, AWS Elemental MediaPackage, and AWS Elemental Live\.
+ **Key Server** – Component of a DRM system that is used to provide keys to the encryptor\.
+ **Operator** – Person in charge of operating the overall system, including the encryptor and the DRM system\.
+ **Player** – Media player operating on behalf of a viewer\. Gets its information from different sources, including the media manifest files, media files, and DRM licenses\. Requests licenses from the DRM server on behalf of the viewers\.

## Related Services and Specifications<a name="related-services-and-specifications"></a>
+ [AWS AssumeRole](https://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRole.html)
+ [API Gateway Permissions](https://docs.aws.amazon.com/apigateway/latest/developerguide/permissions.html)
+ [AWS Sigv4](https://docs.aws.amazon.com/general/latest/gr/sigv4_signing.html)
+ [DASH\-IF CPIX specification](https://dashif.org/docs/DASH-IF-CPIX-v2-0.pdf)
+ [DASH\-IF System IDs](https://dashif.org/identifiers/content_protection/)