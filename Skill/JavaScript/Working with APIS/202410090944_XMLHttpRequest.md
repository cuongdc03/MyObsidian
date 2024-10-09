
| id                          | hubs                            | source                                                                                   |
| --------------------------- | ------------------------------- | ---------------------------------------------------------------------------------------- |
| 202410090944_XMLHTTPRequest | [[hubs/JavaScript\|JavaScript]] | https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest_API/Using_XMLHttpRequest |
To send an HTTP request:
1, Create an `XMLHttpRequest`
2, Open a URL
3, Send the request
After the transaction completes, the `XMLHttpRequest` object will contain useful information such as the response body and the [HTTP status](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) of the result.
```javascript
fucntion reqListener() {
	console.log(this.responseText);
}
const req = new XMLHttpRequest();
req.addEventListener("load",reqListener);
req.open("GET","http://www.example.org/example.txt")
req.send();
```