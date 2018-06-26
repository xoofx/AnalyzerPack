# AnalyzerPack [![Build status](https://ci.appveyor.com/api/projects/status/hk391x8jcskxt1u8?svg=true)](https://ci.appveyor.com/project/xoofx/AnalyzerPack) [![NuGet](https://img.shields.io/nuget/v/AnalyzerPack.svg)](https://www.nuget.org/packages/AnalyzerPack/)

AnalyzerPack is a nuget package that will automatically create a package for your Roslyn Diagnostic Analyzer when performing a `dotnet pack` on your project.

## Why?

Today, when you create a Roslyn Diagnostic Analyzer using the new project format, it can create a NuGet package, but this package is not compatible with a Diagnostic Analyzer package.

For example, your assembly DLL must be moved to the folder `analyzers/dotnet/cs` inside the NuGet package.
You need also to add `tools\install.ps1`, `tools\uninstall.ps1`

By simply referencing AnalyzerPack into your project:

```xml
<PackageReference Include="AnalyzerPack" Version="1.*" PrivateAssets="all" />
```

And when performing a `dotnet pack` on your project (or from Visual Studio), it will automatically generate the proper folder structure for the NuGet diagnostic analyzer.

## Known Limitations

- Might not work with old non SDK project format.
- Your project requires to have only a single `TargetFramework` configured (multiple are not supported)

## License 

MIT

## Author

Alexandre MUTEL aka [xoofx](http://xoofx.com)
