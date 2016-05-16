Communication
===

The communication settings are located under the root `Configuration` node:

```xml
<Configuration>
 
  <!-- ... Previous settings ... -->

  <Communication>
    <!-- Add the http communication channel -->
    <Http Url="http://localhost:50121" />
  </Communication>
  
  <!-- ... Further settings ... -->
 
</Configuration> 
```

The communication node must be set and currently only allows to set the address and port
under which the service is available.

Be port in the configuration is free and usable. The by default delivered port is `50121`.

> Hint: When `localhost` is used, the service is not available in the network and only on
> the local machine. *This behaviour maybe later changes.* 
