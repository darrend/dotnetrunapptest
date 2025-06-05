# Codespaces configuration for .NET 10 Preview

# Use Ubuntu as the base image
FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

# Install .NET 10 Preview SDK
RUN wget https://builds.dotnet.microsoft.com/dotnet/Sdk/10.0.100-preview.4.25258.110/dotnet-sdk-10.0.100-preview.4.25258.110-linux-x64.tar.gz \
    && mkdir -p /usr/share/dotnet \
    && tar -zxf dotnet-sdk-10.0.100-preview.4.25258.110-linux-x64.tar.gz -C /usr/share/dotnet \
    && rm dotnet-sdk-10.0.100-preview.4.25258.110-linux-x64.tar.gz \
    && ln -s /usr/share/dotnet/dotnet /usr/bin/dotnet

# Set up environment variables
ENV DOTNET_ROOT=/usr/share/dotnet
ENV PATH=$PATH:/usr/share/dotnet

# Install common tools
RUN apt-get update && apt-get install -y git curl
