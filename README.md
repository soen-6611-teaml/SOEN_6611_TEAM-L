Metric 1(Statement Coverage), 2(Branch Coverage) and 4(McCabe Complexity) can be calculated by using a code coverage tool like JaCoCo.
Process to measure the metrics:
Step 1: Check if EclEmma plugin is installed in Eclipse. If not, go to Help-> Eclipse Marketplace-> Search for EclEmma-> Install->               Restart Eclipse 
Step 2: Import the maven project to Eclipse. File-> Import -> Existing Maven projects.
Step 3: Add JaCoCo dependency to pom file of the Maven porject.
Step 4: Run the porject as Maven Install and wait for the JaCoCo report to be generated. Code coverage report is generated in HTML, XML         and CSV format. 

# JaCoCo dependency in pom file:
<plugin>
<groupId>org.jacoco</groupId>
<artifactId>jacoco-maven-plugin</artifactId>
<version>0.8.4</version>
<executions>
<execution>
<id>prepare-agent</id>
<goals>
<goal>prepare-agent</goal>
</goals>
</execution>
<execution>
<id>post-unit-test</id>
<phase>test</phase>
<goals>
<goal>report</goal>
</goals>
<configuration>
<!--Sets the path to the file which contains the execution data.-->
<dataFile>target/jacoco.exec</dataFile>
<!--Sets the output directory for the code coverage report.-->
<outputDirectory>target/jacoco-ut</outputDirectory>
</configuration>
</execution>
</executions>
</plugin>

