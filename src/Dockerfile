FROM mcr.microsoft.com/dotnet/sdk:5.0-alpine3.15 AS build
WORKDIR /source
EXPOSE 80
COPY . ./
RUN dotnet restore
RUN dotnet publish -c release -o /app/app_compilado


FROM mcr.microsoft.com/dotnet/aspnet:5.0-alpine3.15
WORKDIR /app
COPY --from=build /app/app_compilado .
ENTRYPOINT ["dotnet", "Review.Web.dll"]
