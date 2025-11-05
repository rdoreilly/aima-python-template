FROM python:3.5-slim

# tools (optional)
RUN apt-get update && apt-get install -y --no-install-recommends \
    git build-essential curl wget ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# keep pip/setuptools/wheel at versions that still support 3.5
RUN python -m pip install --upgrade "pip<21" "setuptools<60" "wheel<0.38"
