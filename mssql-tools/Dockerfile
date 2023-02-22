FROM ubuntu:20.04

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
    curl apt-utils apt-transport-https debconf-utils gcc ca-certificates gnupg2 build-essential iputils-ping dnsutils telnet\
    && curl https://packages.microsoft.com/keys/microsoft.asc | APT_KEY_DONT_WARN_ON_DANGEROUS_USAGE=1 apt-key add - \
    && curl https://packages.microsoft.com/config/ubuntu/20.04/prod.list > /etc/apt/sources.list.d/mssql-release.list \
    && apt-get update && ACCEPT_EULA=Y apt-get install -y --no-install-recommends mssql-tools unixodbc-dev \
    && rm -rf /var/lib/apt/lists/*

ENV PATH="$PATH:/opt/mssql-tools/bin"