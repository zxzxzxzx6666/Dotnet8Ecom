# Ecom
## 簡介
此專案使用 dotnet8 MVC 建置，基於 microsoft eShopOnWeb 專案做進階的優化，使其環境能夠更好的被使用者使用，與更貼近 Production 的環境
## api 使用說明
    1. 先在 api 的資料夾下下指令
    dotnet dev-certs https --trust		
    2. api 另外用 powershell 啟動		
	3. Cors	位置	
    <project location>\src\PublicApi\Program.cs
	更改 line 78	corsPolicyBuilder.WithOrigins(baseUrlConfig!.WebBase.Replace("host.docker.internal", "localhost").TrimEnd('/'), "https://localhost:44315");
	4. SQL 連線
    找到 appsetting.json (此範例為本機資料庫連線字串)	  
    "ConnectionStrings": {
        "CatalogConnection": "Data Source=localhost;Initial Catalog=Microsoft.eShopOnWeb.CatalogDb;Trusted_Connection=True;MultipleActiveResultSets=true;TrustServerCertificate=True;",
        "IdentityConnection": "Data Source=localhost;Initial Catalog=Microsoft.eShopOnWeb.Identity;Trusted_Connection=True;MultipleActiveResultSets=true;TrustServerCertificate=True;"
    },


##### 此專案改自 microsoft eShopOnWeb 專案，非營利所用
##### 此專案不負責任何引用後所造成的損害與損失