Indexing
===

The indexing settings are located under the root `Configuration` node:

```xml
<Configuration>
 
  <!-- ... Previous settings ... -->

  <Indexing>
    <!-- Set redis as the index database -->
    <RedisIndex ConnectionString="127.0.0.1:6379" />

    <!-- Will be executed if the indexing system is not available -->
    <RecoverIndexingSystem>
      <![CDATA[start "redis-server" /D "C:\Program\Simplic\Simplic CDN\Redis\Redis-x64-3.0.501\" redis-server.exe]]>
    </RecoverIndexingSystem>
  </Indexing>
  
  <!-- ... Further settings ... -->
  
</Configuration>
```

The indexing node describes the settings of the indexing system. Currently only `Redis` based indexing is allowed.
The `RedisIndex - ConnectionString` must point to a `Redis-Server`.

The `RecoveryIndexSystem` section will be used to recover the index system, when it is not available. For example
if the CDN is not able to connect to the `Redis-Server`. The `<![CDATA ... ]>` block contains a command line which
will be executed in that case. In the sample above, the system tries to start a redis database server.