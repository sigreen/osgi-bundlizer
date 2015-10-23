OSGi Bundle Maker
=============================

This project creates OSGi bundles from 3rd party library JAR files.  For this example I create 6 OSGi bundles for the Apache QPID JMS Client, allowing me to later deploy them to my OSGi container e.g. Karaf

Execute
---------------------------------------------------------------------

### Run ###
    
(1) Run the following command via the Maven command line:

    shell1> mvn clean install

(2) Via the Karaf console (after starting JBoss A-MQ), run

    shell2> osgi:install -s mvn:osgi.geronimo-jms_1.1_spec/osgi.geronimo-jms_1.1_spec/1.1.1
    shell3> osgi:install -s mvn:osgi.netty-all/osgi.netty-all/4.0.17.Final
    shell4> osgi:install -s mvn:osgi.proton-j/osgi.proton-j/0.10
    shell5> osgi:install -s mvn:osgi.qpid-jms-client/osgi.qpid-jms-client/0.10
    shell6> osgi:install -s mvn:osgi.qpid-jms-discovery/osgi.qpid-jms-discovery/0.6.0
    shell7> osgi:install -s mvn:osgi.slf4j-api/osgi.slf4j-api/0.10
    
There maybe some issues with dependencies e.g. after starting netty-all, so repeat the same command again without the "-s" to prevent startup. This will allow you to install the OSGi bundle without starting it.  Also, if there are any other issues, you can delete the Karaf cache by removing the <a-mq install directory>/data directory.
    