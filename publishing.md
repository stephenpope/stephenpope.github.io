# Publishing Service v2.0 - Quick Start Guide

## Goals

This quick start guide is designed to get you up and running with the **Publishing Service** so that it can be evaluated in a local development environment.
This guide does not go into specific detail about each action. More in-depth information can be found in the full [Installation and Configuration Guide](https://dev.sitecore.net/Downloads/Sitecore_Publishing_Service/20/Sitecore_Publishing_Service_20_Initial_Release.aspx).

The goals of this guide are to:

* Setup the Publishing Service to connect to our Sitecore databases.
* Run the Publishing Service in Development mode.
* Install the Publishing Service package into a clean instance of Sitecore.
* Run a basic publish.
* Install the Publishing Service into IIS.

## Prerequisites and Assumptions

It is assumed that a new/clean version of Sitecore 8.2 Update 2 (rev161221) is installed.

![sim]

**TIP** : Sitecore can be installed quickly and easily using the Sitecore Instance Manager or SIM.
More information can be found on the [Sitecore Instance Manager](https://github.com/Sitecore/Sitecore-Instance-Manager) site.

In this example, we have let SIM automatically install our SQL databases for us and they are named as such (Looking in SQL Management Studio):
 
![sql]

For this guide we have extracted the **Publishing Service** to the path: `C:\PublishingService`

## Configuring the service

Our first step is to tell the **Publishing Service** how to connect to our Sitecore databases so that it can read and write to them.
To do this we will be using the command line. This can either be a PowerShell or normal Command Prompt window.

**NOTE**: The command window must be started as an Administrator in order to perform some of the actions later on.

`Sitecore.Framework.Publishing.Host.exe` : this is the main executable that will run the service but has a set of built-in tools that will help us to set up and configure everything we need.

## Setting up connection string

The **Publishing Service** has a set of `commands` that allow us to perform certain helpful actions as we run and configure the instance.
(More information on commands can be found in Chapter 4 of the [Installation and Configuration Guide](https://dev.sitecore.net/Downloads/Sitecore_Publishing_Service/20/Sitecore_Publishing_Service_20_Initial_Release.aspx))

The first command we will run is `configuration` - this allows us to modify a section of configuration.
It has a special sub-command called `setconnectionstring` specially designed for supplying connection string information that will allow the **Publishing Service** to connect and work with Sitecore databases we have in our setup.

It is invoked as follows:

![config1]

**TIP** : You can find extra information about any command or sub-command by adding `--help` to the end of it.

For our example, we want to setup connection strings for the `web`, `master` and `core` databases.

If we take `core` as our first example. To write the configuration setting we pass the parameters `core` plus our connection string for the core database to the `setconnectionstring` sub-command.

For example:

> .\Sitecore.Framework.Publishing.Host.exe configuration setconnectionstring core 'Data Source=.\SQLEXPRESS;Initial Catalog=sc82rev161221Sitecore_core;Integrated Security=False;User ID=sa;Password=12345;MultipleActiveResultSets=True'

**Note**: It is important that we add `MultipleActiveResltSets=True` to our connections strings so that we can communicate to SQL Server in batches.
More information can be found in the [Installation and Configuration Guide](https://dev.sitecore.net/Downloads/Sitecore_Publishing_Service/20/Sitecore_Publishing_Service_20_Initial_Release.aspx)). 

[sim]: /images/sim.png "SIM installation screenshot"
[sql]: /images/sql.png "SQL Management Studio screenshot"
[config1]: /images/config1.png "Configuration help"