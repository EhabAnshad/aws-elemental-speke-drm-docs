# Payload Components<a name="payload-components"></a>

The request and response payloads for SPEKE vary for live and VOD, but the central components are the same\. You can request responses for one or more DRM systems in each request, specified in the payload's `<cpix:DRMSystemList>`\. For each system specified, you provide the key and indicate the type of response that you want from the DRM key provider\. 

The following example shows a DRM system list with a single DRM system specification: 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/speke/latest/documentation/images/RequestIntroSimple.png)

The following table lists the main components of each `<cpix:DRMSystem>`\.


| Identifier  | Description | 
| --- | --- | 
| systemId or schemeId | Unique identifier for the DRM system type, as registered with the DASH IF organization\. For a list, see [DASH\-IF System IDs](https://dashif.org/identifiers/content_protection/)\. | 
| kid | The key ID\. This is not the actual key, but an identifier that points to the key in a hash table\. | 
| <cpix:UriExtXKey> | Requests a standard unencrypted key\. You request either this common key response or a PSSH response\.  | 
| <cpix:PSSH> | Requests a Protection System Specific Header \(PSSH\)\. This type of header contains a reference to the kid, the systemID, plus custom data for the DRM vendor, as part of Common Encryption \(CENC\)\. You request either a PSSH response or a UriExtXKey response\.  | 

*Example Requests for Standard Key and for PSSH *

The following listing shows part of a sample request from the media encoder to the DRM key provider, with the main components highlighted\. The first request is for a standard key, while the second request is for a PSSH response: 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/speke/latest/documentation/images/RequestIntro1.png)

*Example Responses for Standard Key and for PSSH *

The following listing shows the corresponding response from the DRM key provider to the media encoder: 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/speke/latest/documentation/images/ResponseIntro1.png)