FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build-env
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.sln .
COPY OIDCServer/*.csproj ./OIDCServer/

RUN ls -LR

RUN dotnet restore

# Copy everything else and build
COPY OIDCServer/. ./OIDCServer/

WORKDIR /app/OIDCServer

RUN dotnet publish -c Release -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build-env /app/OIDCServer/out .
ENTRYPOINT ["dotnet", "OIDCServer.dll"]