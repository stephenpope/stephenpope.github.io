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

![alt text][sim]

[sim]: /images/sim.png "SIM installation screenshot"

Sitecore can be installed quickly and easily using the Sitecore Instance Manager or SIM. | test
More information can be found here: [Sitecore Instance Manager](https://github.com/Sitecore/Sitecore-Instance-Manager) |

In this example, we have let SIM automatically install our SQL databases for us and they are named as such (Looking in SQL Management Studio):
 