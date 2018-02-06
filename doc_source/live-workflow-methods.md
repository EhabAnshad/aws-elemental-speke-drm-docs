# Live Workflow Method Calls<a name="live-workflow-methods"></a>

*Request Syntax*

```
POST https://{speke-compatible-server}/speke/v1.0/copyProtection
```

*Request Body*

A CPIX element\.

*Request Headers*


| Name | Type | Occurs | Description | 
| --- | --- | --- | --- | 
| Authorization | String | 1\.\.1 | See [AWS Sigv4](http://docs.aws.amazon.com/general/latest/gr/sigv4_signing.html) | 
| X\-Amz\-Security\-Token | String | 1\.\.1 | See [AWS Sigv4](http://docs.aws.amazon.com/general/latest/gr/sigv4_signing.html) | 
| X\-Amz\-Date | String | 1\.\.1 | See [AWS Sigv4](http://docs.aws.amazon.com/general/latest/gr/sigv4_signing.html) | 
| Content\-Type | String | 1\.\.1 | application/xml | 

*Response Headers*


| Name | Type | Occurs | Description | 
| --- | --- | --- | --- | 
| Speke\-User\-Agent | String | 1\.\.1 | String that identifies the key server | 
| Content\-Type | String | 1\.\.1 | application/xml | 

*Request Response*


| HTTP CODE | Payload Name | Occurs | Description | 
| --- | --- | --- | --- | 
| 200 \(Success\) | CPIX | 1\.\.1 | DASH\-CPIX payload response | 
| 4XX \(Client error\) | Client error message | 1\.\.1 | Description of the client error | 
| 5XX \(Server error\) | Server error message | 1\.\.1 | Description of the server error | 

*Live Example Request*

*Live Example Response*