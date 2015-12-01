# Rackspace Documentation Parent

This project contains a parent **pom.xml** which is referenced by the various
API documentation projects at Rackspace.

## Deployment Setup

In `~/.m2/settings.xml`:

    <settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                      http://maven.apache.org/xsd/settings-1.0.0.xsd">
      <servers>
        <server>
          <id>rackspace-snapshots</id>
          <username>[username]</username>
          <password>[password]</password>
        </server>
        <server>
          <id>rackspace-releases</id>
          <username>[username]</username>
          <password>[password]</password>
        </server>
      </servers>
    </settings>

Then you can deploy with:

    mvn deploy:deploy -Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true -Dmaven.wagon.http.ssl.ignore.validity.dates=true
