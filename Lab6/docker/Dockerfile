FROM ymazieres/dotnet:compile

CMD ["sh", "/script/startScript.sh"]
ENV ASPNETCORE_URLS http://+:5000

COPY /docker/startScript.sh /script/startScript.sh
RUN chmod +x /script/startScript.sh

COPY /src /src

WORKDIR /src
