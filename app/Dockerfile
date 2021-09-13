FROM mcr.microsoft.com/dotnet/sdk AS base

ENV DOTNET_USE_POLLING_FILE_WATCHER 1
ENV ASPNETCORE_URLS=http://+:5000 
EXPOSE 5000

RUN apt-get update \
 && apt-get install -y --no-install-recommends unzip \
 && curl -sSL https://aka.ms/getvsdbgsh | bash /dev/stdin -v latest -l /vsdbg

WORKDIR /app
ENTRYPOINT ["dotnet", "./bin/Debug/net5.0/c2b.net.dll"]