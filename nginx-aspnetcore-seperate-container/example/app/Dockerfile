FROM mcr.microsoft.com/dotnet/core/aspnet:2.2-stretch-slim 
 
WORKDIR /app
COPY bin/Debug/netcoreapp2.2/publish .
 
ENV ASPNETCORE_URLS http://+:5000
EXPOSE 5000
 
ENTRYPOINT ["dotnet", "app.dll"]