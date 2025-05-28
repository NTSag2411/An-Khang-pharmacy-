# --- Giai đoạn Build ---
FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /src

COPY QuanLyNhaThuoc.csproj .
RUN dotnet restore

COPY . .
RUN dotnet publish -c Release -o /app/publish

# --- Giai đoạn Runtime ---
FROM mcr.microsoft.com/dotnet/aspnet:7.0
WORKDIR /app
COPY --from=build /app/publish .

ENTRYPOINT ["dotnet", "QuanLyNhaThuoc.dll"]
