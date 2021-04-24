docker-apex for oracle-xe-11g or oracle-12c
============================

Apex 5.1.2 upgrade package for tekintian/oracle-xe-11g and tekintian/oracle-12c

### Installation

    docker pull tekintian/docker-oracle-apex:5.1.2

Run this to upgrade APEX on you Oracle database container:

    docker run -it --rm --volumes-from ${DB_CONTAINER_NAME} --link ${DB_CONTAINER_NAME}:oracle-database tekintian/docker-oracle-apex:5.1.2 install
    #In that case build woud be with default settings and credentials

Run with custom parameters and credentials:

    docker run -it --rm --volumes-from ${DB_CONTAINER_NAME} --link ${DB_CONTAINER_NAME}:oracle-database -e PASS=SomePassWorD tekintian/docker-oracle-apex:5.1.2 install

The default list of ENV variables is:

    USER=sys
    PASS=oracle
    HOST=oracle-database
    PORT=1521
    SID=XE
    HTTP_PORT=8080

Upgrade might take 10-20 Minutes (Depends on hardware).
