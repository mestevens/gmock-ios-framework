# gmock

## Overview

This is a framework packaged version of Google's gmock c++ library. There are three main components to this packaged version.

- gmock
 	- The actual mocking framework from Google [https://code.google.com/p/googlemock/](https://code.google.com/p/googlemock/)
- gtest
 	- The testing framework from Google [https://code.google.com/p/googletest/](https://code.google.com/p/googletest/)
- xcode-maven-plugin
	- The maven plugin [https://github.com/mestevens/xcode-maven-plugin](https://github.com/mestevens/xcode-maven-plugin) allows you to compile and package this project as a framework easily. Doing so also allows you to include it in another project's pom file as a dependency.
	
## Compiling

Make sure you have maven installed [https://maven.apache.org/](https://maven.apache.org/) and simply run `mvn clean install` from the directory that the pom.xml file is in. This will install this into your local maven repository under the groupId `com.google` and the artifactId `gmock` with version `1.7.0`

## Consuming the framework

After compiling, you can include this into your own project in two different ways.

### With Maven

If your main application is using maven (and the xcode-maven-plugin), you can simply include this as a dependency

```
<dependency>
	<groupId>com.google</groupId>
	<artifactId>gmock</artifactId>
	<version>1.7.0</version>
	<type>xcode-static-framewrok</type>
</dependency>
```

### Without Maven

After compiling, the framework will be found in the `target` directory underneath the root directory (for example if you clone this repository into `/Users/yourname/git/gmock-ios-framework` you could find the framework in `/Users/yourname/git/gmock-ios-framework/target`). Simply copy this framework to where you want it, and include it in your xcode project as you would normally.