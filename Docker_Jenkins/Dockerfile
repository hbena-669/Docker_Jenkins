# Utilise le SDK .NET pour build
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /app
COPY . .
RUN dotnet publish -c Release -o out

# Utilise une image runtime pour exécuter
FROM mcr.microsoft.com/dotnet/runtime:6.0
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "docker_jenkins.dll"]
