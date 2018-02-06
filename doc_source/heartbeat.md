# Heartbeat<a name="heartbeat"></a>

*Request Syntax*

```
GET https://{speke-compatible-server}/speke/v1.0/heartbeat
```

*Request Parameters*


| Name | Type | Occurs | Description | 
| --- | --- | --- | --- | 
| speke\-compatible\-server | String | 1\.\.1 | URL for a TLS\-protected endpoint that supports the API defined in this document | 

*Request Response*


| HTTP CODE | Payload Name | Occurs | Description | 
| --- | --- | --- | --- | 
| 200 \(Success\) | statusMessage | 1\.\.1 | Message that describes the status | 