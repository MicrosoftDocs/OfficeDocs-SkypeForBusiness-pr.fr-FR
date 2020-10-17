---
title: Applets de commande dans Skype entreprise Online qui utilisent le paramètre client
description: Applets de commande dans Skype entreprise Online qui utilisent le paramètre client.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff2b8053dd855a854fa26699770d3dafaa0dcbd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546800"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>Applets de commande dans Skype entreprise Online qui utilisent le paramètre client

 


Lors de la modification de vos paramètres de fournisseur public, vous devez toujours fournir une identité de client ; Cela est vrai même si vous n’avez qu’un seul client. Par exemple, cette commande définit Windows Live en tant que seul fournisseur public avec lequel les utilisateurs sont autorisés à communiquer :

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

Heureusement, il n’est pas nécessaire de taper l’ID de client (par exemple, bf19b7db-6960-41E5-A139-2aa373474354) chaque fois que vous exécutez l’une de ces applets de commande. Au lieu de cela, vous pouvez récupérer l’ID de client en exécutant la cmdlet [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) , en stockant l’ID de client dans une variable, puis en utilisant cette variable lorsque vous appelez l’une des autres cmdlets. Par exemple :

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

Vous pouvez également effectuer cette opération dans une seule commande en récupérant l’ID de client, puis en canalisant cette valeur vers la cmdlet Set-CsTenantPublicProvider :

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

Vous n’avez pas besoin de spécifier l’ID de client lors de l’appel de la cmdlet **Get-CsTenant** . Cette commande retourne des informations sur votre client :

    Get-CsTenant

Les applets de commande suivantes acceptent une identité de client. Toutefois, dans ce cas, le paramètre est facultatif et n’a pas besoin d’être entré lors de l’appel de l’applet de commande. Au lieu de cela, Windows PowerShell entrera l’identité du client à votre place en fonction du client Skype entreprise Online auquel vous êtes actuellement connecté :

  - [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

Par exemple, la cmdlet **Get-CsTenantFederationConfiguration** peut être appelée à l’aide de la commande suivante :

    Get-CsTenantFederationConfiguration

Bien que cela ne soit pas obligatoire, vous pouvez inclure le paramètre client lors de l’appel de Get-CsTenantFederationConfiguration :

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>Voir aussi


[Identités, étendues et locataires dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

