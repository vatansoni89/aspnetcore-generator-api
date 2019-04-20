##Depending on the operating system of the host machines(s) that will build or run the containers, the image specified in the FROM statement may need to be changed.
##For more information, please see https://aka.ms/containercompat
#
#FROM microsoft/aspnetcore:2.0-nanoserver-1803 AS base
#WORKDIR /app
#EXPOSE 80
#
#FROM microsoft/aspnetcore-build:2.0-nanoserver-1803 AS build
#WORKDIR /src
#COPY ["api/api.csproj", "api/"]
#RUN dotnet restore "api/api.csproj"
#COPY . .
#WORKDIR "/src/api"
#RUN dotnet build "api.csproj" -c Release -o /app
#
#FROM build AS publish
#RUN dotnet publish "api.csproj" -c Release -o /app
#
#FROM base AS final
#WORKDIR /app
#COPY --from=publish /app .
#ENTRYPOINT ["dotnet", "api.dll"]

From microsoft/aspnetcore

WORKDIR /app
COPY bin/Debug/netcoreapp2.0/publish .

ENTRYPOINT ["dotnet","api.dll"]

#docker build -t aspnetcore/generator .
#(it will look for Dockerfile in project folder and follow the instructions, . => current directory)
#
#run image in container:
#docker run --rm -it -p 8080:80 aspnetcore/generator