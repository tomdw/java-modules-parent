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

In your project which you want to build using java 11 compatible maven plugins, use the following snippet as maven parent:

```xml
<parent>
	<groupId>io.github.tomdw.java.modules</groupId>
	<artifactId>java-modules-parent</artifactId>
	<version>0.0.3</version>
	<relativePath />
</parent>
```

### Add version to module-info.class

To make sure that the module version is also added to the module-info.class a preconfigured execution of the exec-maven-plugin is available that updates the jar with the module version.
 
You need to add this to the module build (if exec-maven-plugin is already listed, then the extra configuration will be picked up):

```xml
	<build>
		<plugins>
			<plugin>
				<groupId>org.codehaus.mojo</groupId>
				<artifactId>exec-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>
```

The `jar` tool will be automatically used to update the module-info.class inside the jar with the maven project version.