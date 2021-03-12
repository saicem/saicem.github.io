# Serilog

```cs
Log.Logger = new LoggerConfiguration()
  .MinimumLevel.Debug()
  .WriteTo.Console()
  .WriteTo.File($"logs/Log_.txt", rollingInterval: RollingInterval.Month)
  .CreateLogger();
```

# .NET

自定义端口

```cs
webBuilder.UseUrls("http://+:5917");
  webBuilder.UseSetting("https_port", "5918");
  webBuilder.UseStartup<Startup>();
```