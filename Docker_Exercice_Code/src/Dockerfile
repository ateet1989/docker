FROM mcr.microsoft.com/dotnet/core/sdk:3.1
WORKDIR /src
COPY ["dotnet-jenkins-demo/dotnet-jenkins-demo.csproj", "dotnet-jenkins-demo/"]
RUN dotnet restore "dotnet-jenkins-demo/dotnet-jenkins-demo.csproj"
COPY . .
WORKDIR "/src/dotnet-jenkins-demo"
RUN dotnet build "dotnet-jenkins-demo.csproj" -c Release -o /app
RUN dotnet publish "dotnet-jenkins-demo.csproj" -c Release -o /app
EXPOSE 80
WORKDIR /app
ENTRYPOINT ["dotnet", "dotnet-jenkins-demo.dll"]