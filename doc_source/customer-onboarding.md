# Customer Onboarding<a name="customer-onboarding"></a>

Protect your content from unauthorized use by combining a digital rights management \(DRM\) system key server with your AWS Elemental media services and with your media players\. Follow the steps in this chapter to get started using encryption with your AWS Elemental media services\. 

## Step 1: Check Supported Technologies<a name="check-supported-technologies"></a>

The following tables show supported technologies\. Verify that your streaming protocol and the DRM system that you want are available for your live or VOD service\. 


**AWS Elemental MediaPackage: Streaming Protocol / DRM System Support Matrix**  

|  | Microsoft PlayReady | Google Widevine | Apple Fairplay | AES\-128 | 
| --- | --- | --- | --- | --- | 
| DASH | √ with key rotation | √ with key rotation |  |  | 
| Apple HLS |  |  | √ | √ with key rotation | 
| Microsoft Smooth | √ |  |  |  | 


**AWS Elemental MediaConvert: Streaming Protocol / DRM System Support Matrix**  

|  | Microsoft Playready | Google Widevine | Apple Fairplay | AES\-128 | 
| --- | --- | --- | --- | --- | 
| DASH | √ | √ |  |  | 
| Apple HLS |  |  | √ | √ | 
| Microsoft Smooth | √ |  |  |  | 

## Step 2: Get On Board with an AWS DRM Solution Provider<a name="choose-drm-system"></a>

The following Amazon partners provide third\-party DRM system implementations for AWS Elemental products\. For details about each solution provider's offerings and information about how to contact them, follow the links to their Amazon Partner Network pages\. The partners will help you get set up to use their solutions with AWS Elemental media services\. 

+ [BuyDRM](https://aws.amazon.com/partners/find/partnerdetails/?n=BuyDRM&id=001E000000UfZXLIA3) 

+ [Castlabs](https://aws.amazon.com/partners/find/partnerdetails/?n=castLabs&id=001E000001Bv2lcIAB)

+ [Conax AS](https://aws.amazon.com/partners/find/partnerdetails/?n=Conax%20AS&id=0010L00001nEJPEQA4)

+ [EZDRM](https://aws.amazon.com/partners/find/partnerdetails/?n=EZDRM&id=001E000000UfZgxIAF)

+ [Irdeto](https://aws.amazon.com/partners/find/partnerdetails/?n=Irdeto&id=001E000000Rl0x2IAB)

+ [Verimatrix](https://aws.amazon.com/partners/find/partnerdetails/?n=Verimatrix&id=001E000000be2SEIAY)

We use a standard key exchange protocol, which is documented in our Secure Packager and Encoder Key Exchange \(SPEKE\) Digital Rights Management \(DRM\) specification at [[ERROR] BAD/MISSING LINK TEXT](speke-api-specification.md)\. Our DRM solution providers have integrated with AWS Elemental media services by exposing a SPEKE\-compliant REST API\. 