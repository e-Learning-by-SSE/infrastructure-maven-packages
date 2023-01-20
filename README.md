# Maven Packages for Student-Management-System Organization

This repository is used as a central location to publish packages with maven.

## Setup

This needs to be done once if you work with maven dependencies of this organization.

1. Create a token under https://github.com/settings/tokens with the scopes `repo`, `write:packages`, and `read:packages`.

2. Add the following to `~/.m2/settings.xml` (`~` refers to your home directory, e.g. `C:\Users\USERNAME\` under Windows):
```xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 http://maven.apache.org/xsd/settings-1.0.0.xsd">

	<activeProfiles>
		<activeProfile>github</activeProfile>
	</activeProfiles>

	<profiles>
		<profile>
			<id>github</id>
			<repositories>
				<repository>
					<id>central</id>
					<url>https://repo1.maven.org/maven2</url>
					<releases>
						<enabled>true</enabled>
					</releases>
					<snapshots>
						<enabled>true</enabled>
					</snapshots>
				</repository>
				<repository>
					<id>student-management-system-github</id>
					<name>e-learning GitHub Packages</name>
					<url>https://maven.pkg.github.com/e-learning-by-sse/mavenpackages</url>
					<releases>
						<enabled>true</enabled>
					</releases>
					<snapshots>
						<enabled>true</enabled>
					</snapshots>
				</repository>
			</repositories>
		</profile>
	</profiles>

	<servers>
		<server>
			<id>student-management-system-github</id>
			<username>USERNAME</username>
			<password>TOKEN</password>
		</server>
	</servers>
</settings>
```
**Note:** Replace `USERNAME` and `TOKEN` with your GitHub username and the token you generated in step 1.
