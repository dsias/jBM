# jBM - Online Bookmark Manager

jBM is a Java Web Application to collect your bookmarks online.

Add bookmarks with a bookmarklet, the web gui or an Android app.

jBM is a Java port of [SemanticScuttle](https://sourceforge.net/projects/semanticscuttle/) and contains some code of it.

# License

[GNU General Public License, version 2](https://www.gnu.org/licenses/gpl-2.0.html)

# Setup

## Database

create a PostgreSQL database for jBM and execute the [tables-postgresql.sql](entities/src/main/resources/tables-postgresql.sql) script. 

    createdb jbm
    psql jbm < entities/src/main/resources/tables-postgresql.sql 

## Tomcat 

add these driver jars to tomcat/lib

* postgresql-9.4.1212.jar
* javax.persistence-2.1.1.jar
* eclipselink-2.6.4.jar

add a jBM-custom.properties to tomcat/lib like

    javax.persistence.jdbc.driver=org.postgresql.Driver
    javax.persistence.jdbc.url=jdbc:postgresql://host/jbm
    javax.persistence.jdbc.user=jbm
    javax.persistence.jdbc.password=sosecret

### Security

jBM needs JEE Security Roles

    jBM
    jBMAPI

jBMAPI for the remote API (for the Android App).

For Tomcat these are declared in tomcat-users.xml

    <role rolename="jBM"/>
    <role rolename="jBMAPI"/>
    <user username="weberjn" password="sosecret" roles="jBM,jBMAPI"/>


# Screenshots

#### list Bookmarks

![list Bookmarks](doc/bookmarks.png?raw=true)

#### add a Bookmark

![add a Bookmark](doc/addbookmark.png?raw=true)

# API

jBM supports a subset of the delicious API v1.

# Android

[Scuttloid](https://github.com/ilesinge/scuttloid) can be used as Android Client for jBM.

Server-URL is your jBM context root

    http://your.host/jBM

    




