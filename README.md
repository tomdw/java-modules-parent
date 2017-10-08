# java-modules-parent
Simple Maven parent pom setup for building java 9 modulepath based projects

## How to use

### Toolchains

To make sure that the right java version installed on your system is used, 
we make sure of the maven toolchain support.

You need to create a **toolchains.xml** of which an example can be found under 
/toolchain/toolchains.xml. Adapt the paths of the JDK-homes to your local 
development machine and copy this file next to your settings.xml on your 
local machine. For example inside the  ~/.m2 directory. 

### Use as parent

In your project which you want to build using java 9 compatible maven plugins, use the following snippet as maven parent:

```xml
<parent>
	<groupId>be.tomdewolf.jpms</groupId>
	<artifactId>java-modules-parent</artifactId>
	<version>1.0.0</version>
	<relativePath />
</parent>
```
