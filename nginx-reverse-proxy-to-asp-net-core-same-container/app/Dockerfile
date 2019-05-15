
FROM microsoft/dotnet:2.2.0-aspnetcore-runtime

RUN printf "deb http://archive.debian.org/debian/ jessie main\ndeb-src http://archive.debian.org/debian/ jessie main\ndeb http://security.debian.org jessie/updates main\ndeb-src http://security.debian.org jessie/updates main" > /etc/apt/sources.list

RUN apt-get update
RUN apt-get install -y nginx
 
WORKDIR /app
COPY bin/Debug/netcoreapp2.2 .
 
COPY ./startup.sh .
RUN chmod 755 /app/startup.sh
 
RUN rm /etc/nginx/nginx.conf
COPY nginx.conf /etc/nginx
 
ENV ASPNETCORE_URLS http://+:5000
EXPOSE 5000 80

#RUN service nginx start
#ENTRYPOINT ["dotnet", "app.dll"]

CMD ["sh", "startup.sh"]