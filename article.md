The purpose of this article is to give some guidance on how to send metrics from a Spring application to Wavefront, a.k.a. Tanzu Observability.
The simplest way to use metrics from a Spring app running in PCF is probably to use the App Metrics tile.
However, that depends on the client having the tile available.
Additionally, with Wavefront being a strategic focus for the company,
learning how to send metrics to the tool can help us make things easy for our clients.
I'm aware of three straightforward ways to export metrics from an app running in Cloud Foundry to Wavefront.
The first, and most general approach is to use the Wavefront for Spring Boot starter and configure it to send metrics to your client's Wavefront instance.
This is relatively simple, but requires that each app using Wavefront be configured to use the tool.
It may be the only way to connect to Wavefront if your client doesn't make a tile available with which to integrate.
The latest official version of the Wavefront Nozzle tile (3.0.4 at the time of this writing) makes a service broker available,
which apps can bind to and use to export metrics to VMWare.
Finally, the beta for version 4 of the Wavefront Nozzle tile does not provide a service broker, but automatically makes basic Request/Error/Duration(RED) metrics available in Wavefront with no extra configuration required.
The nice thing about both tile options is that they do not require any knowledge of how to configure an application to connect to Wavefront,
as this is done either through a service binding abstraction,
or completely automatically.
