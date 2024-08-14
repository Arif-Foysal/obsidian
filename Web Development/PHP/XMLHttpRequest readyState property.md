#xml #http 

The **XMLHttpRequest.readyState** property returns the state an XMLHttpRequest client is in. An XHR client exists in one of the following states:

|Value|State|Description|
|---|---|---|
|`0`|`UNSENT`|Client has been created. `open()` not called yet.|
|`1`|`OPENED`|`open()` has been called.|
|`2`|`HEADERS_RECEIVED`|`send()` has been called, and headers and status are available.|
|`3`|`LOADING`|Downloading; `responseText` holds partial data.|
|`4`|`DONE`|The operation is complete.|

[UNSENT](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState#unsent)

The XMLHttpRequest client has been created, but the open() method hasn't been called yet.

[OPENED](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState#opened)

open() method has been invoked. During this state, the request headers can be set using the [setRequestHeader()](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/setRequestHeader) method and the [send()](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/send) method can be called which will initiate the fetch.

[HEADERS_RECEIVED](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState#headers_received)

send() has been called, all redirects (if any) have been followed and the response headers have been received.

[LOADING](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState#loading)

Response's body is being received. If [`responseType`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseType) is "text" or empty string, [`responseText`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseText) will have the partial text response as it loads.

[DONE](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState#done)

The fetch operation is complete. This could mean that either the data transfer has been completed successfully or failed.

## [Example](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState#example)

JSCopy to Clipboard

```
const xhr = new XMLHttpRequest();
console.log("UNSENT", xhr.readyState); // readyState will be 0

xhr.open("GET", "/api", true);
console.log("OPENED", xhr.readyState); // readyState will be 1

xhr.onprogress = () => {
  console.log("LOADING", xhr.readyState); // readyState will be 3
};

xhr.onload = () => {
  console.log("DONE", xhr.readyState); // readyState will be 4
};

xhr.send(null);
```

