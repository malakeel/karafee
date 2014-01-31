# Karaf EE

Karaf EE project is a packaging of the Karaf Standalone Container (2.x) with EJB & CDI technology. Currently it supports these Apache implementations of the EJB 3 spec and CDI 1.0 : [OpenEJB](http://openejb.apache.org/) and [OpenWebbeans](http://openwebbeans.apache.org/) 

## Build 

- Prerequisite

The Karaf feature file `openejb` which contains the modules (bundles, configurations files, ...) that we will use for KarafEE project must be installed locally in your local maven repo as this file is not longer maintained by OpenEJB - TomEE project

Copy [feature.xml](http://search.maven.org/remotecontent?filepath=org/apache/openejb/openejb-feature/4.5.2/openejb-feature-4.5.2-features.xml) to your local repository

```
.m2/repository/org/apache/openejb/openejb-feature/4.5.2
```

- Build the project

```
mvn clean install
```
