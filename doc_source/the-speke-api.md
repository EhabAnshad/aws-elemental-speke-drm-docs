# SPEKE API<a name="the-speke-api"></a>

To work with AWS Elemental products, your key server must expose the REST API described in this specification\. The encryptor makes API calls to your key server\.

**Note**  
The code examples in this specification are for illustration purposes only\. You can’t run the examples because they aren’t part of a complete SPEKE implementation\. 

SPEKE uses the DASH Industry Forum Content Protection Information Exchange Format \(DASH\-IF\-CPIX\) data structure definition for key exchange\. DASH\-IF\-CPIX defines a schema to provide an extensible, multi\-DRM exchange from the DRM system to the encryptor\. This enables content encryption for all adaptive bitrate packaging formats at the time of content compression and packaging\. Adaptive bitrate packaging formats include HLS, DASH, and MSS\. 

For detailed information about the exchange format, see the DASH Industry Forum CPIX specification at [https://dashif\.org/docs/DASH\-IF\-CPIX\-v2\-0\.pdf](https://dashif.org/docs/DASH-IF-CPIX-v2-0.pdf)\.

The SPEKE API payload response conforms to DASH\-IF\-CPIX with the following constraints and customizations:
+ SPEKE follows the Encryptor Consumer workflow\.
+ SPEKE does not use the encrypted document feature\. Instead, it relies on encryption at the transport layer, plus strong authentication\.
+ For rotating key workflows, SPEKE requires the `ContentKeyUsageRule` filter, `KeyPeriodFilter`\. SPEKE ignores all other `ContentKeyUsageRule` settings\.
+ SPEKE omits the `UpdateHistoryItemList` functionality\. If the list is present in the response, SPEKE ignores it\. 
+ SPEKE supports key rotation\. SPEKE uses only the `ContentKeyPeriod` `@index` to track the key period\.
+ To support MSS PlayReady, SPEKE uses a custom parameter under the `DRMSystem` tag, `SPEKE:ProtectionHeader`\.
+ For HLS packaging, if the `URIExtXKey` is present in the response, then it must contain the full data to add in the URI parameter of the `EXT-X-KEY` tag of an HLS playlist, with no further signaling requirement\.
+ For HLS playlist, under the `DRMSystem` tag, SPEKE provides the optional custom parameters `speke:KeyFormat` and `speke:KeyFormatVersions`, for the values of the `KEYFORMAT` and `KEYFORMATVERSIONS` parameters of the `EXT-X-KEY` tag\.

  The HLS IV always follows segment number unless explicitly specified by the operator\.
+ When requesting keys, the encryptor might use the optional `@explicitIV` attribute on the `ContentKey` element\. The key server can respond with an IV using `@explicitIV`, even if the attribute is not included in the request\.
+ The encryptor creates the key identifier \(`KID`\), which stays the same for any given content ID and key period\. The key server includes the `KID` in its response to the request document\.
+ The key server might include a value for the `Speke-User-Agent` response header, to identify itself for debugging purposes\.
+ SPEKE does not currently support multiple tracks or keys per content\.

The AWS Elemental encryptor acts as a client and sends `POST` operations to the key server endpoint\. The encryptor might send a periodic `heartbeat` request to ensure that the connection between the encryptor and the key server endpoint is healthy\.