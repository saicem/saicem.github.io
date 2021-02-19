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

### 额外的问题

- 程序不要乱起名！出了问题都找不到原因！
- 如果一个解决方案有多个项目，要确保所有项目都能成功编译，不然会`Add-Migration`会报错。
- Microsoft.EntityFrameworkCore.Design 有时需要有时不需要，目前不清楚。
- CodeFirst时需要先添加主键，如果表中含有id属性，则id默认为主键。
- 在创建表时，如果没有额外设置，除了字符串均为非null。

### 更多

#### More than one DbContext was found. Specify which one to use. Use the '-Context' parameter for PowerShell commands and the '--context' parameter for dotnet commands.

```
add-migrations Initial -context DemoDbContext
```

忘了再看 [安装EF Core](https://docs.microsoft.com/zh-cn/ef/core/get-started/overview/install)