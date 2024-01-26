# C\#

## code first

### 步骤

1. 安装 Entity Framework Core tools
   - Get the .NET Core CLI tools
   `dotnet tool install --global dotnet-ef`
   - Get the Package Manager Console tools
   `Install-Package Microsoft.EntityFrameworkCore.Tools`

2. 完成数据库的设置
   - 安装EF Core nuget包
   - 创建实体类及上下文
   - 配置appsettings.json
   - 配置Startup.cs

3. 使用以下命令生成Migrations 并生成数据库(程序包管理器控制台)

```c#
Install-Package Microsoft.EntityFrameworkCore.Tools
Add-Migration InitialCreate
Update-Database
```

忘了再看 [安装EF Core](https://docs.microsoft.com/zh-cn/ef/core/get-started/overview/install)

## 生成Api文档(xml)

项目 -> 属性 -> 输出 -> 文档文件 生成包含API文档的文件

```C#
services.AddSwaggerGen(c =>
{
  var xmlFile = $"{Assembly.GetExecutingAssembly().GetName().Name}.xml";
  var xmlPath = Path.Combine(AppContext.BaseDirectory, xmlFile);
  c.IncludeXmlComments(xmlPath);
});
```

## 数据库

- `ConnectionStrings__AppDb` `Server=?;Database=?;Uid=?;Pwd=?;` 参考 [connectionstrings.com](https://www.connectionstrings.com/mysql/)

## ASP.NET 环境变量

- `{Scheme}://{ServiceHost}:{ServicePort}` 可以用在 launchUrl
- `ASPNETCORE_URLS` [设置监听端口](https://learn.microsoft.com/zh-cn/aspnet/core/fundamentals/minimal-apis?view=aspnetcore-7.0#set-the-ports-via-the-aspnetcore_urls-environment-variable)

### 在 Linux 上转义环境变量

使用 `systemd-escape` 命令
