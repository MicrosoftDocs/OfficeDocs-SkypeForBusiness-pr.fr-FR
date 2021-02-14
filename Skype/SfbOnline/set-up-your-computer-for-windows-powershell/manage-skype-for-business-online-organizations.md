---
title: Gérer les organisations Skype Entreprise Online
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
description: Utilisez Windows PowerShell, les Get-CsTenant et Get-CsTenantLicensingConfiguration de clients pour obtenir des informations sur votre client Skype Entreprise Online.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085690"
---
# <a name="manage-skype-for-business-online-organizations"></a>Gérer les organisations Skype Entreprise Online
> [!NOTE]
> La dernière version [d’aperçu public de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et fournit un seul module pour la gestion de Teams PowerShell.

Vous pouvez trouver des informations sur votre client Skype Entreprise Online à l’aide des cmdlets **Get-CsTenant** et **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Gérer les clients Skype Entreprise Online

Pour renvoyer des informations sur votre client Skype Entreprise Online, appelez l’cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sans aucun paramètre supplémentaire.
  
```PowerShell
Get-CsTenant
```

Pour renvoyer uniquement le nom et l’ID du client, utilisez cette commande.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

La valeur du paramètre _TenantID_ est requise lors de l’exécution d’lets telles que [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) et [Set-CsTenantFederationConfiguration.](https://technet.microsoft.com/library/jj994080.aspx)
  
Pour déterminer si les informations de licence du client spécifié sont disponibles dans le Centre d’administration Skype Entreprise Online, utilisez l’cmdlet [Get-CsTenantLicensingConfiguration.](https://go.microsoft.com/fwlink/p/?linkid=849606)
  
## <a name="related-topics"></a>Sujets associés
[Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
