Add This to your pom in the 

&lt;build&gt;

 

&lt;plugins&gt;

 section

```
                        <plugin>
				<groupId>org.jboss.maven.plugins</groupId>
				<artifactId>maven-jdocbook-plugin</artifactId>
				<version>2.3.5</version>
				<extensions>true</extensions>
				<dependencies>
					<dependency>
				      		<groupId>org.mobicents.jdocbook</groupId>
				      		
				      		<artifactId>telestax-xslt-ns</artifactId>
				      		<version>1.2.0</version>
				    	</dependency>
				    	<dependency>
				      		<groupId>org.mobicents.jdocbook</groupId>
				      		<artifactId>telestax-community-style</artifactId>
				      		<type>jdocbook-style</type>
				      		<version>1.2.0</version>
				    	</dependency>
				</dependencies>
				<configuration>					
					<sourceDocumentName>SIP_Balancer_User_Guide.xml</sourceDocumentName>
					<sourceDirectory>${project.build.directory}/docbook/resources</sourceDirectory>
					<imageResource>
						<directory>${project.build.directory}/docbook/resources/en-US</directory>
						<includes>
							<include>images/*</include>
						</includes>
					</imageResource>
					<formats>
						<format>
							<formatName>pdf</formatName>
							<stylesheetResource>classpath:/xslt/org/jboss/pdf.xsl</stylesheetResource>
							<finalName>SIP_Balancer_User_Guide.pdf</finalName>
						</format>
						<format>
							<formatName>html</formatName>
							<stylesheetResource>classpath:/xslt/org/jboss/xhtml.xsl</stylesheetResource>
							<finalName>index.html</finalName>
						</format>
						<format>
							<formatName>html_single</formatName>
							<stylesheetResource>classpath:/xslt/org/jboss/xhtml-single.xsl</stylesheetResource>
							<finalName>index.html</finalName>
						</format>
					</formats>
					<options>
				        	<xmlTransformerType>saxon</xmlTransformerType>
              					<xincludeSupported>true</xincludeSupported>
              					<docbookVersion>1.72.0</docbookVersion>
              					<useRelativeImageUris>true</useRelativeImageUris>
            				</options>		
				</configuration>			
			</plugin>
```

You can use TelScale jdocbook for product style
```
                                        <dependency>
                                                <groupId>org.mobicents.jdocbook</groupId>
                                                <artifactId>telestax-telscale-style</artifactId>
                                                <type>jdocbook-style</type>
                                                <version>1.2.0</version>
                                        </dependency>
```

instead of

```
                                        <dependency>
                                                <groupId>org.mobicents.jdocbook</groupId>
                                                <artifactId>telestax-community-style</artifactId>
                                                <type>jdocbook-style</type>
                                                <version>1.2.0</version>
                                        </dependency>
```