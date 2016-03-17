Install and uninstall a service
===

One machine can run multiple `Simplic CDN` services at the same time. Those services are separated with a name, which is placed behind the service name.

## Install new service

To install a new service, start a Windows command line with administrative privileges. After that, navigate to the `Simplic Content Delivery Network`
installation directory. Typically this located under `C:\Progam\Simplic\Simplic Content Delivery Network\`. To install the service, the `Simplic.CDN.exe`
has to be started with the `--install` argument:

```
Simplic.CDN.exe --install
```

Using this, a service with the name `Simplic CDN` will be registered. If you want to register a nother instance of the service, use the `--name` argument:

```
Simplic.CDN.exe --install --name AnotherConfig
```

The name of the service must be the same as the configuration directory in the following path: `<Installation-Path>/Configuration/<Service-Name>`.
If no name argument is set, the default configuration will be used.

## Uninstall service

To uninstall a service use the `--uninstall` argument. All other steps are the same as shown in `Install new service` above.

---

> [!NOTE]
> The default installer will always create a service with the name `Simplic CDN` using the default configuration.
>
>If you creating a complete new configuration, make a copy of the `template` configuration directory and start editing `Configuration.config`.
>This is the best way to create a new configuration, because it already contains all section which are needed.