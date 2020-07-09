---
title: Gestion des organisations Skype entreprise Online
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
description: Utilisez Windows PowerShell et les applets de connexion Get-CsTenant et Get-CsTenantLicensingConfiguration pour obtenir des informations sur votre client Skype entreprise online.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085690"
---
# <a name="manage-skype-for-business-online-organizations"></a>Gestion des organisations Skype entreprise Online
> [!NOTE]
> La [version d’évaluation publique PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) la plus récente est intégrée au connecteur Skype entreprise Online pour proposer un module unique pour la gestion d’teams PowerShell.

Vous pouvez trouver des informations sur votre client Skype entreprise Online à l’aide des applets de connexion **Get-CsTenant** et **Get-CsTenantLicensingConfiguration** .
  
## <a name="manage-skype-for-business-online-tenants"></a>Gestion des locataires Skype entreprise Online

Pour renvoyer des informations sur votre client Skype entreprise Online, appelez l’applet de connexion [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sans aucun paramètre supplémentaire.
  
```PowerShell
Get-CsTenant
```

Pour renvoyer uniquement le nom du client et l’ID, utilisez la commande suivante.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

La valeur du paramètre _IDClient_ est requise lors de l’exécution de cmdlets telles que [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) et [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).
  
Pour savoir si des informations de licence pour le client spécifié sont disponibles dans le centre d’administration Skype entreprise Online, utilisez l’applet de connexion [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>Voir aussi
[Configurer votre ordinateur pour la gestion de Skype entreprise Online à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
