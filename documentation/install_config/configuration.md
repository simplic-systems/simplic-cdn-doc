Simplic CDN Configuration
===

The simplic cdn is placed in a single configuration which is located under `<application directory>/Simplic CDN/Configuration/<configuration-name>/Configuration.config`.
All configurations are splitted into a few sections:

- General Settings
- Index settings
- Security settings
- Communication settings
- Storage settings

All configurations are writtin in `xml`.

> Hint: Often it is usefull to comment the configuration using xml comments.

To run a simplic cdn with a specific configuration, it must be started using the configuration name in the `--name` attribute: `Simplic.CDN.exe --name <configuration-name>`. 

When starting the Simplic CDN it should start when no configuration issues exists. If some configuration is wrong,
it will be written to the command line or in the log file located under `%localappdata%\Simplic CDN\Log\<configuration>\Simplic-CDN.log`.