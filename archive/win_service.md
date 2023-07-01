# Windows 服务编写

如果使用 C/C++ 编写，参考 [Service Program Tasks](https://learn.microsoft.com/en-us/windows/win32/services/service-program-tasks)

## msix 声明服务

Capabilities 声明以下权限

```xml
<Capabilities>
  <rescap:Capability Name="localSystemServices" />
  <rescap:Capability Name="packagedServices" />
</Capabilities>
```

Application 下声明

```xml
<Extensions>
  <desktop6:Extension Category="windows.service" EntryPoint="Windows.FullTrustApplication" Executable="TimuseService.exe">
    <desktop6:Service Name="Timuse Service" StartAccount="localService" StartupType="auto" />
  </desktop6:Extension>
</Extensions>
```

引用 desktop6 `xmlns:desktop6="http://schemas.microsoft.com/appx/manifest/desktop/windows10/6"`
