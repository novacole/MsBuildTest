### MSBuild Test Target

Assuming a stub target "Test" exists in Microsoft.Common.CurrentVersion.targets
```
<!-- 
    ***********************************************************************************************
    ***********************************************************************************************
                                                                Test Section
    ***********************************************************************************************
    ***********************************************************************************************
-->
  <Target Name="Test">
  </Target>

```

Setup

* Build, then add this nuget package to the test projects
* Import test target into Directory.Build.targets or similiar
```
<Import Project="$(USERPROFILE)\.nuget\packages\microsoft.msbuildtest\1.0.0\sdk\MsBuildTest.target" />

```
Execute Tests
```
$env:MSBUILDENSURESTDOUTFORTASKPROCESSES=1
msbuild /nodereuse:false /t:Test
```

