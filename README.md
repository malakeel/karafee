# Karaf EE

Karaf EE project is a packaging of the Karaf Standalone Container (2.3.1) with EJB & CDI technology. Currently it supports these Apache implementations of the EJB 3 spec and CDI 1.0 : [OpenEJB](http://openejb.apache.org/) and [OpenWebbeans](http://openwebbeans.apache.org/) 

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

During the build process, a Karaf distribution will be generated. This zip/tar.gz files are available under the directory `target/`.

- Run KarafEE

Unzip/untar the karafEE distribution, move to the bin directory in your terminal and launch `./karafee` command
Karaf Container will be launched in standalone mode and the console will appear soon

```

```

You can verify that OpenEJB & CDI is well deployed using this command


- Make a test

TODO - Add links to [EJB & CDI examples](http://openejb.apache.org/examples-trunk/simple-stateless/README.html)
