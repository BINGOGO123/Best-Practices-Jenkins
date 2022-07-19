# testbase-console-jenkins

This is a console application sample of Jenkins azure-testbase-plugin. `Program.cs`, `HeightGained.sln` and `HeightGained.csproj` are the source code needed to build the installer. `Scripts` contains four test scripts. `Jenkinsfile` has pre-defined several steps of the build process, and the last step is to onboard the package with azure-testbase-plugin.

`TestBase.json` is the configuration file for azure-testbase-plugin which contains mandatory parameters for this plugin. You can write configuration in this file in advance. And if you don't want to use this kind of extra configuration file to configure azure-testbase-plugin, you can also congifure these options during the creation of freestyle job or generate pipeline statement from syntax generator.

## build the installer

Make sure you have installed [dotnet](https://www.nuget.org/downloads) and [neget](https://www.nuget.org/downloads)

```shell
dotnet restore
dotnet build --configuration Release --no-restore
```