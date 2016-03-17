
HTTP-Api introduction
===

The http api allows to communicate with the `Simplic CDN` ussing `http/1.1`. The RESTful API contains all public methods, for
working with the system. The api is available under the following address: 

```
<your-address>/api/v1-0/<<controller>>/<<method>>
```

For example

```
http://localhost:50121/api/v1-0/cdn/ping
```

The controller is marked as the top-level node in the documentation. For example: `/cdn/`. All sub-nodes are available methods.