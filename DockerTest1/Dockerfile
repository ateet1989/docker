FROM mcr.microsoft.com/dotnet/core/sdk:2.2
WORKDIR /
COPY ["DockerTest1/DockerTest1.csproj", "DockerTest1/"]
RUN dotnet restore "DockerTest1/DockerTest1.csproj"
COPY . .
WORKDIR "/DockerTest1"
RUN dotnet build "DockerTest1.csproj" -c Release -o /app
RUN dotnet publish "DockerTest1.csproj" -c Release -o /app
EXPOSE 80
WORKDIR /app
ENTRYPOINT ["dotnet", "DockerTest1.dll"]