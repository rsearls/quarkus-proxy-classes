Issue resolved by upgrade to quarkus 1.3.0.Alpha1

# quarkus-proxy-classes
Tests show error "method is not visible from class loader".  This occurrs for proxy classes.

Resteasy has a lot of test classes that creates a proxy class from an interface
definition.  The quarkus environment reports, "method is not visible from class loader".
and the test fails.


Before running the test install this archive in your local repo.
Here is the cmd to do it.

mvn install:install-file \
   -Dfile=___FIX_THIS___/lib/utils-arquillian-utils-4.5.0-SNAPSHOT.jar \
   -DgroupId=org.jboss.resteasy \
   -DartifactId=utils-arquillian-utils \
   -Dversion=4.5.0-SNAPSHOT \
   -Dpackaging=jar 

Execution env.
    jdk 11.0.2
    mvn 3.6.0
    quarkus 1.2.0.Final
    
  The pom.xml file contains the minimum archives required to compile and run the tests.
  
  This project shows 2 tests that presents this error.  See pom.xml
  file lines 249 and 251
  
  compile the project
       mvn clean test -DskipTests=true
       
  run the tests
       mvn test
       
  A file containing the stacktrace is provided in xstacktrace-proxy.txt         
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
