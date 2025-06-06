# Codespaces configuration for .NET 10 Preview

# Use Ubuntu as the base image
FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

# Install .NET 10 Preview SDK for the detected architecture
ARG DOTNET_SDK_VERSION=10.0.100-preview.4.25258.110
RUN ARCH=$(dpkg --print-architecture) \
    && if [ "$ARCH" = "arm64" ]; then \
        DOTNET_PKG=dotnet-sdk-${DOTNET_SDK_VERSION}-linux-arm64.tar.gz; \
      else \
        DOTNET_PKG=dotnet-sdk-${DOTNET_SDK_VERSION}-linux-x64.tar.gz; \
      fi \
    && wget https://builds.dotnet.microsoft.com/dotnet/Sdk/${DOTNET_SDK_VERSION}/$DOTNET_PKG \
    && mkdir -p /usr/share/dotnet \
    && tar -zxf $DOTNET_PKG -C /usr/share/dotnet \
    && rm $DOTNET_PKG \
    && ln -s /usr/share/dotnet/dotnet /usr/bin/dotnet

# Set up environment variables
ENV DOTNET_ROOT=/usr/share/dotnet
ENV PATH=$PATH:/usr/share/dotnet

# Install common tools
RUN apt-get update && apt-get install -y git curl
