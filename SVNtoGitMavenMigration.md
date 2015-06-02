# Modifications to the POMs #

A couple of changes are needed in the pom when you migrate from the old SVN repo located at http://code.google.com/p/mobicents/source/checkout to your new repo on Git

## General Information ##

Make sure to point the url tag in your pom to the new repo as shownbelow (replace sipservlets with your project name)

```
<url>http://code.google.com/p/sipservlets/</url>
```

## Repositories ##

Add the following repository to your pom's repositories tag

```
                 <repository>
			  <id>mobicents-public-repository-group</id>
			  <name>Mobicents Public Maven Repository Group</name>
                           <url>https://oss.sonatype.org/content/groups/public</url>
			  <layout>default</layout>
			  <releases>
			    <enabled>true</enabled>
			    <updatePolicy>never</updatePolicy>
			  </releases>
			  <snapshots>
			    <enabled>true</enabled>
			    <updatePolicy>never</updatePolicy>
			  </snapshots>
		</repository>
```

## Parent Pom ##

Make your parent POM project inherit from the latest version (2.22 or 2.23-SNAPSHOT at the time of this writing) as shown below

```
        <parent>
		<artifactId>mobicents-parent</artifactId>
		<groupId>org.mobicents</groupId>
		<version>2.23-SNAPSHOT</version>
	</parent>
```

## SCM Information ##

You need to point your SCM information to your git repo as shown below (replace sipservlets with your project name)

```
        <scm>
		<connection>scm:git:https://code.google.com/p/sipservlets/</connection>
		<developerConnection>scm:git:https://code.google.com/p/sipservlets/</developerConnection>
		<url>https://code.google.com/p/sipservlets/</url>
	</scm>
```

# CI Job Migration #

Migrate your CI jobs from http://ci.jboss.org/jenkins/view/Mobicents/ to https://mobicents.ci.cloudbees.com/