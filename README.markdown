Introduction
============

This project contains a Google AppEngine project that :

* has a servlet implementing the PayPal IPN "protocol" (Instand Payment Notification)
* persists all IPN messages (and parses them partially)
* uses postback validation
* a minimal Vaadin application to browse the stored IPN messages

Keep in mind that the PayPal sandbox can be pretty slow. So you might get timeouts on validation messaages (GAE has a set 10s max timeout)

Feel free to fork this project and improve it. I'd love to see some cooperation on taming the PayPal beast :)


Getting started
===============

Configure your Appengine SDK
---------------------------- 

in .m2/settings.xml:

    <settings>
      <profiles>
        <profile>
          <id>gae-config</id>
          <properties>
            <gae.home>C:\Java\lib\appengine-java-sdk-1.5.4</gae.home>
          </properties>
        </profile>
      </profiles>
      <activeProfiles>
        <activeProfile>gae-config</activeProfile>
      </activeProfiles>
    </settings>

Build and run the example application
-------------------------------------

1. `mvn clean install`
2. `cd war`
3. `mvn gae:run`


Maven repository
================

The current snapshot is hosted on Sonatype's snapshot repository, so if you just want to use the project add this to your pom.xml:

    <repositories>
		<repository>
			<id>sonatype-snapshots</id>
			<name>Sonatype Open Source snapshot repository (for POW and MailJimp)</name>
			<url>https://oss.sonatype.org/content/groups/public/</url>
		</repository>
	</repositories>
	<dependencies>
		<dependency>
			<groupId>com.pow.paypal</groupId>
			<artifactId>pow-paypal-core</artifactId>
			<version>0.0.1-SNAPSHOT</version>
		</dependency>
    </dependencies>   