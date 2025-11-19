FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS base
WORKDIR /app
EXPOSE 8080

FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src
COPY ["src/FileStorage.API/FileStorage.API.csproj", "src/FileStorage.API/"]
COPY ["src/FileStorage.Application/FileStorage.Application.csproj", "src/FileStorage.Application/"]
COPY ["src/FileStorage.Domain/FileStorage.Domain.csproj", "src/FileStorage.Domain/"]
COPY ["src/FileStorage.Infrastructure/FileStorage.Infrastructure.csproj", "src/FileStorage.Infrastructure/"]
RUN dotnet restore "src/FileStorage.API/FileStorage.API.csproj"
COPY . .
WORKDIR "/src/src/FileStorage.API"
RUN dotnet build "FileStorage.API.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "FileStorage.API.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "FileStorage.API.dll"]

