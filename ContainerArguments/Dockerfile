FROM microsoft/dotnet:2.1-aspnetcore-runtime AS base
WORKDIR /app
EXPOSE 80

FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /src
ARG inputfolder='ContainerArguments'
ARG outputfolder=''
COPY ${inputfolder}/ContainerArguments.csproj ContainerArguments/
RUN dotnet restore ContainerArguments/ContainerArguments.csproj
COPY . .${outputfolder}
WORKDIR /src/ContainerArguments
RUN dotnet build ContainerArguments.csproj -c Release -o /app

FROM build AS publish
RUN dotnet publish ContainerArguments.csproj -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "ContainerArguments.dll"]
