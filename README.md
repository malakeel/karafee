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

During the build process, a Karaf distribution will be generated. This tar.gz file is available under the directory `apache-karafee/target/`.

- Run KarafEE

Untar the karafEE distribution `tar -vxf apache-karafee-1.0-SNAPSHOT.tar.gz`, move to the bin directory of `apache-karafee-1.0-SNAPSHOT/bin` in your terminal and launch `./karafee` command
Karaf Container will be launched in standalone mode and the console will appear soon

```
./karafee
     __ __              ___________
    / //_/__ ________ _/ _/ __/ __/
   / ,< / _ `/ __/ _ `/ _/ _// _/
  /_/|_|\_,_/_/  \_,_/_//___/___/

  Apache KarafEE (1.0-SNAPSHOT)

Hit '<tab>' for a list of available commands
and '[cmd] --help' for help on a specific command.
Hit '<ctrl-d>' or 'osgi:shutdown' to shutdown KarafEE.
```

You can verify that OpenEJB & CDI is well deployed and some EJB beans have already been registered using this command

```
openejb:list
=========================================================================================================================================================================================
           Name            |                             Class                             |                                 Interface Type                                 | Bean Type |
=========================================================================================================================================================================================
 openejb/ConfigurationInfo | org.apache.openejb.assembler.classic.cmd.ConfigurationInfoEjb | Remote[[interface org.apache.openejb.assembler.classic.cmd.ConfigurationInfo]] | STATELESS |
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
           MEJB            |               org.apache.openejb.mgmt.MEJBBean                |                                                                                | STATELESS |
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
     openejb/Deployer      |           org.apache.openejb.assembler.DeployerEjb            |           Remote[[interface org.apache.openejb.assembler.Deployer]]            | STATELESS |
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
       openejb/User        |           org.apache.openejb.assembler.util.UserEjb           |           Remote[[interface org.apache.openejb.assembler.util.User]]           | STATELESS |
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
```

- Make a test

TODO - Add links to [EJB & CDI examples](http://openejb.apache.org/examples-trunk/simple-stateless/README.html)
