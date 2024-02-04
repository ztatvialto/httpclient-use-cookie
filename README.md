Results

```
first resp: {      
  "cookies": {     
    "aff": "node1" 
  }                
}                  

second resp: {     
  "cookies": {     
    "aff": "node1" 
  }                
}                  

new client resp: { 
  "cookies": {}
}

```

## How to turn off cookie for httpclient?

```csharp
var noCookieHandler = new HttpClientHandler();
noCookieHandler.UseCookies = false;
var client = new HttpClient(noCookieHandler);
```
