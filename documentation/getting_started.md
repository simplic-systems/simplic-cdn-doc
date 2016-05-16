Getting started
===
The gettings started tutorial contains a few steps which has to be followed for setting up a very basic simplic cdn installation.

## Download

Download the latest `Simplic CDN` release from [http://cdn.simplic-systems.com/downloads](http://cdn.simplic-systems.com/downloads).

## Installation

Start the simplic-cdn wizard and follow the installation instructions. The installer is very simple and will guide you through
the basic file-deployment. At this step no configuration will be done.

Be sure, you're also installing the `Redis` feature.

## Basic configuration

All configurations are store inside of the `Configuration` directory in the root application folder.
In general this is located under `C:\Program\Simplic\Simplic-CDN\`. If no parameters will be passed
to the `simplic.cdn.exe`, it will use the default configuration. To use the configuration for the 
*Getting Started Tutorial*, following these steps:

### 1. Start a redis session

Navigate the the `Redis/Redis-x64-3.0.501` directory in the application directory of the `simplic cdn` and start,
`redis-server.exe`.

> For producte systems the configuration file as to be adjusted, to have all security options set.

### 2. Create and start mongodb

Download the newest mongodb version that fits to your os from [mongodb-download](https://www.mongodb.com/download-center#community) and install
it on your system. To setup an empty mongodb for the tutorial, start the windows `cmd.exe` with administrative
access and execute the following command: `mongod --dbpath <<db-path>> --port 27017`. Please replace `<<db-path`>>
with a real path on your system. At this place the mongo-deamon will store the database.

> Do not create a mongodb with this settings for productive systems, because this databases can be access
> without any user authentications.

### 3. Start the demo configuration

To start the demo configuration which is deliverd with the default setup, start the `cmd.exe` and navigate
into the simplic cdn program directory. In the directory, the cdn must be started using this command: `simplic.cdn.exe --name getting_started`.
Now the cdn should start without any errors. If any errors occures, try to solve them or feel free to contact us. 

## Connect to the server

To connect with the server, start `cdn-shell.exe` and enter the connect command: 
`connect --url 'http://localhost:50121/api/v1-0/' --uid admin --pwd cdn`. When you've logged in successfully,
you should get a success messsage.

### Send data to the cdn

To send data to the storage, execute the following command: `send --name 'sample.data' --path '<<path-to-the-demo-file>>'`

### Read data from the cdn

To read data from the storage, execute the following command: `read --name 'sample.data' --path '<<path-to-store-data-in>>'`