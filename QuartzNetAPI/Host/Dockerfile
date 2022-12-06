FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS runtime
WORKDIR /app
EXPOSE 80
RUN apt-get update && apt-get install -y tzdata
#RUN apt-get update && apt-get install -y icu-libs
ENV DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=false
RUN cp /usr/share/zoneinfo/Asia/Taipei /etc/localtime
RUN cp /usr/share/zoneinfo/Asia/Taipei /usr/share/zoneinfo/Asia/Beijing
COPY published/ ./
ENTRYPOINT ["dotnet", "Host.dll"]