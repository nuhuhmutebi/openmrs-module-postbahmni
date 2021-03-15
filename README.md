# OpenMRS Post Bahmni module

Bahmni post-runner module to apply corrective Liquibase changesets that straighten Bahmni non-identifiable metadata entities.

## Description
Post Bahmni module essentially consists of a [single Liquibase file](./api/src/main/resources/liquibase.xml) that ensures metadata created by other modules with dynamic UUIDs will have a fixed, known UUID.

It will most likely be used in combination with an OpenMRS Configuration (processed via [OpenMRS Initializer](https://github.com/mekomsolutions/openmrs-module-initializer)) so that one can override the metadata using the now fixed UUIDs.

Note that running the module will **override the existing UUIDs**, meaning it could have **unexpected consequences** if your previous UUIDs are referenced elsewhere, for instance as Global Properties values, application.properties files or any other places.


## Building from Source
```
git clone https://github.com/mekomsolutions/openmrs-module-postbahmni
cd openmrs-module-postbahmni
mvn clean package
```
