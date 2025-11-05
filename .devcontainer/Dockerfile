FROM python:3.5-slim

# Point apt to Debian archive (buster is EOL) and install minimal tools
RUN set -eux; \
    sed -i 's|deb.debian.org|archive.debian.org|g' /etc/apt/sources.list; \
    sed -i 's|security.debian.org|archive.debian.org|g' /etc/apt/sources.list; \
    printf 'Acquire::Check-Valid-Until "false";\nAcquire::AllowInsecureRepositories "true";\n' \
      > /etc/apt/apt.conf.d/99archive; \
    apt-get update; \
    apt-get install -y --no-install-recommends \
        git build-essential curl wget ca-certificates; \
    rm -rf /var/lib/apt/lists/*

# Keep tools that still support Python 3.5
RUN python -m pip install --upgrade "pip<21" "setuptools<60" "wheel<0.38"
