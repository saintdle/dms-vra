# Integrating Data Management for VMware Tanzu with vRealize Automation using Dynamic Types

File repository for configuring vRealize Automation workflows to interact with Data Management for VMware Tanzu to provide Self-Service capabilities within vRA Service Broker.

Full technical walkthrough on how to configure these packages:

>    Blog Post - http://vexpert.me/dms-tanzu-vra
>     
>    Recording - https://youtu.be/L_3DcejGKzM

## High Level Steps

Within vRO:

* Import "com.vmware.dms.backup.package" on the packages UI
* Update REST Host to point to your correct URL
* Update the Configuration Asset "DMS - Login Details" with appropiate username and password (ORG Admin user needed)
* Import "dynamictypes-config.package" using the appropiate workflow
Within vRA
* Create a custom resource pointing to the appropiate LifeCycle Actions
* Link Day 2 Actions
* Create a cloud template that consumes the Custom Resource
* Release cloud template to the service broker, configure catalog item to use vRO action "get_configuration_values" to populate the template version as a drop down list for the user to select from
