---
title: Runnable jar File for JavaFX App with Maven
excerpt: "Build a stand-alone, runnable jar file using Maven."
description: "Build a stand-alone, runnable jar file using Maven."
categories: [Development]
tags: [java, javafx, maven, fat jar]
---

Unlike Java Swing or AWT GUI applications, a JavaFX application needs a litte more tweaking to generate a fat jar that contains all dependencies and that can be run as a stand-alone application.

I used to use the maven assembly plugin to generate runnable jars.  I'm pretty sure it's possible but I could not find a setup that works for JavaFX Apps.

Instead, came up with the following setup, using the [maven-shade-plugin](https://maven.apache.org/plugins/maven-shade-plugin/) and the [javafx-maven-plugin](https://github.com/openjfx/javafx-maven-plugin):

1.  First, we need a main class that does not exend from `javafx.application.Application`. We introduce a small helper class that delegates to the *real* application class:

        public class Launcher {
            public static void main(String[] args) {
                MyApplication.main(args);
            }
        }

    The *real* main class:

        public class MyApplication extends Application {
            public static void main(String[] args) {
                launch(args);
            }
        }

2. Next, the Maven Shade plugin:

            <plugin>
				<artifactId>maven-shade-plugin</artifactId>
				<version>3.2.4</version>
				<executions>
					<execution>
						<phase>package</phase>
						<goals>
							<goal>shade</goal>
						</goals>
						<configuration>
							<outputFile>shade/MyApp-${project.version}.jar</outputFile>
							<transformers>
								<transformer implementation="org.apache.maven.plugins.shade.resource.ManifestResourceTransformer">
									<mainClass>com.github.myapp.Launcher</mainClass>
								</transformer>
							</transformers>
						</configuration>
					</execution>
				</executions>
			</plugin>

3. The Maven plugin for JavaFX:

            <plugin>
				<groupId>org.openjfx</groupId>
				<artifactId>javafx-maven-plugin</artifactId>
				<version>0.0.8</version>
				<configuration>
					<mainClass>com.github.myapp.MyApplication</mainClass>
				</configuration>
			</plugin>

4. Done! you can now trigger a Maven install, which will generate the runnable jar file during the build.
