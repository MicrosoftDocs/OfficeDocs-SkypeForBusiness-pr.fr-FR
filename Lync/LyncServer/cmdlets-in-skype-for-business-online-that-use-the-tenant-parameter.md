---
title: Cmdlets dans Skype entreprise Online utilisant le paramètre locataire
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa3b09e6f419c7425332427ccf4a4ff664b9e395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838089"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>Cmdlets dans Skype entreprise Online utilisant le paramètre locataire

 


Lorsque vous modifiez les paramètres de votre fournisseur public, vous devez toujours fournir une identité de client; C’est vrai, même si vous n’avez qu’un seul client. Par exemple, cette commande définit Windows Live en tant que seul fournisseur public auquel les utilisateurs sont autorisés à communiquer:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

Heureusement, vous n’avez pas besoin de taper l’ID de locataire (par exemple, bf19b7db-6960-41E5-A139-2aa373474354) chaque fois que vous exécutez l’une de ces applets de connexion. Au lieu de cela, vous pouvez récupérer l’ID de locataire en exécutant l’applet de demande [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) , en stockant l’ID de locataire dans une variable, puis en utilisant cette variable lorsque vous appelez l’une des autres cmdlets. Par exemple :

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

Vous pouvez également effectuer cette opération dans une seule commande en récupérant l’ID de locataire, puis en canalisant cette valeur vers l’applet de commande Set-CsTenantPublicProvider:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

Vous n’avez pas besoin de spécifier l’ID de locataire lorsque vous appelez l’applet **de action Get-CsTenant** . Cette commande renvoie des informations sur votre client:

    Get-CsTenant

Les applets de commande suivantes acceptent une identité de client. Néanmoins, dans ces cas-là, le paramètre est facultatif et n’a pas besoin d’être entré lorsque vous appelez l’applet de cmdlet. Au lieu de cela, Windows PowerShell entrera efficacement l’identité du client en fonction du client Skype entreprise Online auquel vous êtes actuellement connecté:

  - [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

Par exemple, vous pouvez appeler l’applet de commande **Get-CsTenantFederationConfiguration** à l’aide de la commande suivante:

    Get-CsTenantFederationConfiguration

Même si ce n’est pas obligatoire, vous pouvez inclure le paramètre locataire lors de l’appel de Get-CsTenantFederationConfiguration:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>Voir aussi


[Identités, étendues et clients dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

