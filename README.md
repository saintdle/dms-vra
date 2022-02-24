# Integrating Data Management for VMware Tanzu with vRealize Automation using Dynamic Types

File repository for configuring vRealize Automation workflows to interact with Data Management for VMware Tanzu to provide Self-Service capabilities within vRA Service Broker.

Full technical walkthrough on how to configure these packages:

>    Blog Post 
>    - [Data Management for VMware Tanzu with vRealize Automation as Custom Resources](http://vexpert.me/dms-tanzu-vra)
>       - Updated Feb 2022 - now includes the changes needed to support DMS v1.1
>    - [How to create vRO Dynamic Types for vRA Custom Resources](http://vexpert.me/vra-dynamic-types)
>    
>    Recording 
>    - YouTube - [Integrating Data Management for VMware Tanzu with vRealize Automation](https://youtu.be/L_3DcejGKzM)

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

![](https://i0.wp.com/veducate.co.uk/wp-content/uploads/2021/09/DMS-Create-DB-operation-Completed.jpg?resize=768%2C448&ssl=1)
