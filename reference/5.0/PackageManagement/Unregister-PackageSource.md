---
ms.date:  06/09/2017
schema:  2.0.0
locale:  en-us
keywords:  powershell,cmdlet
online version:  http://go.microsoft.com/fwlink/?LinkID=517143
external help file:  Microsoft.PowerShell.PackageManagement.dll-Help.xml
title:  Unregister-PackageSource
---

# Unregister-PackageSource

## SYNOPSIS
Removes a registered package source.

## SYNTAX

### SourceBySearch
```
Unregister-PackageSource [[-Source] <String>] [-Location <String>] [-Credential <PSCredential>] [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### SourceByInputObject
```
Unregister-PackageSource -InputObject <PackageSource[]> [-Credential <PSCredential>] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PSModule:SourceByInputObject
```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-PackageManagementProvider <String>] [-Scope <String>] [-PublishLocation <String>] [<CommonParameters>]
```

### PSModule:SourceBySearch
```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-PackageManagementProvider <String>] [-Scope <String>] [-PublishLocation <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-PackageSource** cmdlet removes a registered package source.
Package sources are always managed by a package provider.

## EXAMPLES

### Example 1: Unregister a package source for the Nuget provider
```
PS C:\> Unregister-PackageSource -Source "MyRep" -Location "http://contoso/nuget/MyRepository/api/v3" -Provider "Nuget"
```

This command unregisters a package source named Features for the Nuget provider.
You are prompted to confirm that you want to unregister the package because the *Force* parameter is not specified,

### Example 2: Unregister a package source by using a PackageSource object
```
PS C:\> $A = Get-PackageSource -Name "MyRep" -Location "http://contoso/nuget/Features/api/v3"
PS C:\> Unregister-PackageSource -InputObject $A -Force
```

This command unregisters a package source named Features for the Nuget provider by saving the results of a **Get-PackageSource** command to a variable, and then using the variable as input to **Unregister-PackageSource**.
The *Force* parameter ensures that you are not prompted to confirm that you want to unregister the package.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user account that has rights to unregister a package source for a specified package provider.
Specify a user name, such as User01, or Domain\User01, or specify a **PSCredential** object, such as one generated by the Get-Credential cmdlet.
The simplest way to specify a **PSCredential** object is to save the results of a **Get-Credential** cmdlet as a variable.
When you add this parameter and specify a user name, you are prompted to provide a password after you run the command.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceBootstrap
Indicates that this cmdlet forces Package Management to automatically install the package provider for the specified package source.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies a package source by using the package source's object, which is shown in the results of the Get-PackageSource cmdlet.

```yaml
Type: PackageSource[]
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Location
Specifies the location to which a package source points.
The value of this parameter can be a URI, a file path, or any other destination format that is supported by the package provider.

```yaml
Type: String
Parameter Sets: SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageManagementProvider
Specifies the Package Management provider.

```yaml
Type: String
Parameter Sets: PSModule:SourceByInputObject, PSModule:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderName
Specifies the provider name.

```yaml
Type: String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: msi, Programs, msu, Bootstrap, PSModule, nuget, chocolatey

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublishLocation
Specifies the publish location.

```yaml
Type: String
Parameter Sets: PSModule:SourceByInputObject, PSModule:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scope
Specifies the scope of the Package Source. The acceptable values for this parameter are: AllUsers and CurrentUser. 

```yaml
Type: String
Parameter Sets: PSModule:SourceByInputObject, PSModule:SourceBySearch
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
Specifies the friendly name of the package source.

```yaml
Type: String
Parameter Sets: SourceBySearch
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### You cannot pipe input to this cmdlet.

## OUTPUTS

### This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_packagemanagement.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Set-PackageSource](Set-PackageSource.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)
