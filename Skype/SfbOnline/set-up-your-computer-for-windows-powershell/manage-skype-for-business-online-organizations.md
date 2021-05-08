---
title: Gérer Skype Entreprise organisations Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Utilisez Windows PowerShell, les Get-CsTenant et Get-CsTenantLicensingConfiguration de compte pour obtenir des informations sur votre client Skype Entreprise Online.
ms.openlocfilehash: 2fa95bf8997dd0aff7271b1383c69d9b27c4f4a9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238784"
---
# <a name="manage-skype-for-business-online-organizations"></a>Gérer Skype Entreprise organisations Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> La dernière version Teams version d’aperçu [public de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et fournit un module unique pour la Teams PowerShell.

Vous pouvez trouver des informations sur votre client Skype Entreprise Online à l’aide des cmdlets **Get-CsTenant** et **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Gérer Skype Entreprise client en ligne

Pour renvoyer des informations sur votre Skype Entreprise Online, appelez l’cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) sans aucun paramètre supplémentaire.
  
```PowerShell
Get-CsTenant
```

Pour renvoyer uniquement le nom et l’ID du client, utilisez cette commande.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

La valeur du paramètre _TenantID_ est requise lors de l’exécution d’lets telles que [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) et [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)
  
Pour déterminer si les informations de licence du client spécifié sont disponibles dans le Centre d’administration Skype Entreprise Online, utilisez l’cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)
  
## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
