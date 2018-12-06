---
title: Applets de commande utilisant le paramètre Tenant
TOCTitle: Applets de commande utilisant le paramètre Tenant
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56269668
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Applets de commande utilisant le paramètre Tenant

 

_**Dernière rubrique modifiée :** 2015-06-22_

Lorsque vous modifiez vos paramètres de fournisseur public, vous devez toujours fournir une identité Tenant. Ceci s’applique même si vous n’avez qu’un seul client. Par exemple, la commande suivante définit Windows Live comme seul fournisseur public avec lequel vos utilisateurs sont autorisés à communiquer :

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

Heureusement, vous n’avez pas besoin de taper l’ID de client (par exemple, bf19b7db-6960-41e5-a139-2aa373474354) chaque fois que vous exécutez une de ces applets de commande. Vous pouvez simplement récupérer l’ID de client en exécutant l’applet de commande [Get-CsTenant](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenant), en stockant celui-ci dans une variable, puis en utilisant cette variable lorsque vous appelez une des autres applets de commande. Par exemple :

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

Vous pouvez également utiliser une seule commande pour ce faire en récupérant l’ID de client et en redirigeant la valeur vers l’applet de commande Set-CsTenantPublicProvider :

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

Vous n’avez pas besoin de spécifier l’ID de client lorsque vous appelez l’applet de commande **Get-CsTenant**. Cette commande retourne des informations sur votre client :

    Get-CsTenant

Les applets de commande suivantes acceptent une identité de client. Dans ces cas, le paramètre est facultatif et n’a pas besoin d’être entré lorsque l‘applet de commande est appelée. Windows PowerShell entre en effet l’identité du client automatiquement sur la base du client Skype Entreprise Online auquel vous êtes connecté actuellement :

  - [Get-CsTenant](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenant)

  - [Set-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantFederationConfiguration)

  - [Set-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTenantHybridConfiguration)

  - [Get-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantFederationConfiguration)

  - [Get-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantHybridConfiguration)

  - [Get-CsTenantLicensingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantLicensingConfiguration)

Par exemple, l’applet de commande **Get-CsTenantFederationConfiguration** peut être appelée à l’aide de la commande suivante :

    Get-CsTenantFederationConfiguration

Bien que cela ne soit pas requis, vous pouvez inclure le paramètre Tenant lorsque vous appelez l’applet de commande Get-CsTenantFederationConfiguration :

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## Voir aussi

#### Concepts

[Identités, étendues et clients](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande de Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

