Hej Hej!

Are you dealing with this Exception???

## Exception in thread "main" java.lang.NoClassDefFoundError: org/codehaus/plexus/util/xml/Xpp3DomBuilder$InputLocationBuilder 

I've been stuck with this for two days and finally found the answer.
Here are my sources: 
+ https://github.com/ere-health/dgc-ps-app/issues/6
+ https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=948286

SO basically the problem is that tha maven-helper library didn+t update the version of the dependency ibplexus-utils2-java 
due to a bug. THe way to solve 
this is to add the depencensy on the POM related to the module.

JUst copy the following on the dependecy section :
        <dependency>
            <groupId>org.codehaus.plexus</groupId>
            <artifactId>plexus-utils</artifactId>
            <version>3.5.0</version>
        </dependency>
        

Because you might read this in the future you need to make sure this is the version you want,
so take a look at what MAven repository says about this library-> [link](https://mvnrepository.com/artifact/org.codehaus.plexus/plexus-utils) 


🐼 :_Best, [Sofi](https://github.com/Sofi1410)_
