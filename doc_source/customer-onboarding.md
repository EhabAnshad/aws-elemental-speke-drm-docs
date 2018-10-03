# Customer Onboarding<a name="customer-onboarding"></a>

Protect your content from unauthorized use by combining a digital rights management \(DRM\) system key server with your AWS Elemental encoders and with your media players\. Follow the steps in this chapter to get started using encryption\. 

**Topics**
+ [Step 1: Check Supported Technologies](#check-supported-technologies)
+ [Step 2: Get On Board with a DRM Solution Provider](#choose-drm-system)

## Step 1: Check Supported Technologies<a name="check-supported-technologies"></a>

The following support matrices show the DRM system support for each streaming protocol\. Verify that your streaming protocol and the DRM system that you want are available for your AWS Elemental service or product\.

------
#### [ AWS Elemental MediaConvert ]


|  | Microsoft PlayReady | Google Widevine | Apple FairPlay | AES\-128 | 
| --- | --- | --- | --- | --- | 
| DASH | √ | √ |  |  | 
| Apple HLS |  |  | √ | √ | 
| Microsoft Smooth | √ |  |  |  | 

------
#### [ AWS Elemental MediaPackage ]


|  | Microsoft PlayReady | Google Widevine | Apple FairPlay | AES\-128 | 
| --- | --- | --- | --- | --- | 
| DASH | √ with key rotation | √ with key rotation |  |  | 
| Apple HLS |  |  | √ with key rotation | √ with key rotation | 
| Microsoft Smooth | √ |  |  |  | 
| CMAF Apple HLS |  |  | √ with key rotation |  | 

------
#### [ AWS Elemental Live ]


|  | Microsoft PlayReady | Google Widevine | Apple FairPlay | AES\-128 | 
| --- | --- | --- | --- | --- | 
| DASH | √ | √ |  |  | 
| Apple HLS TS |  |  | √ with key rotation | √ with key rotation | 
| Apple HLS fMP4 |  |  | √ with key rotation |  | 

------

## Step 2: Get On Board with a DRM Solution Provider<a name="choose-drm-system"></a>

The following Amazon partners provide third\-party DRM system implementations for AWS Elemental products\. For details about each solution provider's offerings and information about how to contact them, follow the links to their Amazon Partner Network pages\. Partners that don't have a link don't currently have an Amazon Partner Network page, but you can contact them directly\. The partners can help you get set up to use their solutions with AWS Elemental media services and products\. 
+ Axinom
+ [BuyDRM](https://aws.amazon.com/partners/find/partnerdetails/?n=BuyDRM&id=001E000000UfZXLIA3) 
+ [castLabs](https://aws.amazon.com/partners/find/partnerdetails/?n=castLabs&id=001E000001Bv2lcIAB)
+ [Conax AS](https://aws.amazon.com/partners/find/partnerdetails/?n=Conax%20AS&id=0010L00001nEJPEQA4)
+ [EZDRM](https://aws.amazon.com/partners/find/partnerdetails/?n=EZDRM&id=001E000000UfZgxIAF)
+ [INKA Entworks](https://aws.amazon.com/partners/find/partnerdetails/?n=INKA%20Entworks%20Inc%2C&id=001E000000qGr8GIAS)
+ [Irdeto](https://aws.amazon.com/partners/find/partnerdetails/?n=Irdeto&id=001E000000Rl0x2IAB)
+ [Kaltura](https://aws.amazon.com/partners/find/partnerdetails/?n=Kaltura&id=001E000000Rp5FnIAJ)
+ NEXTSCAPE, Inc\.
+ [Verimatrix](https://aws.amazon.com/partners/find/partnerdetails/?n=Verimatrix&id=001E000000be2SEIAY)

AWS uses a standard key exchange protocol, which is documented in our Secure Packager and Encoder Key Exchange \(SPEKE\) Digital Rights Management \(DRM\) specification at [SPEKE API Specification for DRM Solution Providers](speke-api-specification.md)\. Each Amazon partner who provides a third\-party DRM system implementation for AWS Elemental products exposes a SPEKE\-compliant REST API to the partner's key servers\. 