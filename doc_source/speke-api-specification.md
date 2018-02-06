# SPEKE API Specification for DRM Solution Providers<a name="speke-api-specification"></a>

This is the REST API specification for AWS Elemental Secure Packager and Encoder Key Exchange \(SPEKE\)\. Use this specification to write a REST API for your digital rights management \(DRM\) system key server that is compatible with AWS Elemental MediaConvert and AWS Elemental MediaPackage\. 

In a video streaming workflow, the encryption engine communicates with the DRM system key store to request content keys\. These keys are highly sensitive, so it is critical that the key store and encryption engine establish a highly secure, trusted communication channel\. 

This specification addresses the following goals: 

+ Define a simple, trusted, highly secure interface that DRM vendors and customers can use to integrate with AWS Elemental products when content encryption is required\. 

+ Cover VOD and live workflows, and include the error conditions and the authentication mechanisms that are required for robust, highly secure communication between AWS Elemental products and DRM key server endpoints\.

+ Include support for HLS, MSS, and DASH packaging and their common DRM systems \(Fairplay, PlayReady, and Widevine/CENC\)\.

+ Keep the specification simple and extensible, to support future DRM systems\.

+ Use a simple REST API\.