Source

```csharp
var client = new HttpClient();
var setCookieUrl = "https://httpbin.org/cookies/set/aff/node1";
var listCookiesUrl = "https://httpbin.org/cookies";

var resp = await client.GetAsync(setCookieUrl);
Console.WriteLine($"first resp: {await resp.Content.ReadAsStringAsync()}");

var secondResp = await client.GetAsync(listCookiesUrl);
Console.WriteLine($"second resp: {await secondResp.Content.ReadAsStringAsync()}");

var newClientResp = await new HttpClient().GetAsync(listCookiesUrl);
Console.WriteLine($"new client resp: {await newClientResp.Content.ReadAsStringAsync()}");
```

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
