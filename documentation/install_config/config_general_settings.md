General Settings
===

General settings are located directly under the root element:

```xml
<Configuration>

  <!-- General settings -->
  <Settings>
    <!-- If it is set to true, the system will copy all blobs to the primary system if the primary system was not accessable
    and a fallback-system was used -->
    <RestoreOnFallback Value="true" />
    <AlloDeleteBlobs Value="false" />

  </Settings>
 
 <!-- ... some more configuration sections ... -->
 
</Configuration>
```

Currently it allows to configuration whether deleting data is allowed and if the cdn should
automatically recover data, which are saved in a `FallBackStorage`. That means, if data are stored
in a `FallBackStorage` during a period of time when all `PrimaryStorages` were unavailable,
they will automatically copied back to a primary storage if they are available.

> Hint: Declaring a storage to `PrimaryStorage` or `FallbackStorage` can also be used, for easily migrating data
> from an *ADO.Net storage* to a *mongo-db storage* or any other storage type.