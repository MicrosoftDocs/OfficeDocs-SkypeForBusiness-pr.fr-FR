---
title: Gérer les Skype pour les organisations Business en ligne
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Utiliser Windows PowerShell et les applets de commande Get-CsTenant et Get-CsTenantLicensingConfiguration pour obtenir des informations sur votre Skype pour client d’entreprise en ligne.
ms.openlocfilehash: b71c89967ab34909fa461f71fc5f67c1cf99a408
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32224444"
---
# <a name="manage-skype-for-business-online-organizations"></a>Gérer les Skype pour les organisations Business en ligne

Vous trouverez des informations sur votre Skype pour client d’entreprise en ligne à l’aide des applets de commande **Get-CsTenant** et **Get-CsTenantLicensingConfiguration** .
  
## <a name="manage-skype-for-business-online-tenants"></a>Gérer les Skype pour les clients professionnels en ligne

Pour retourner des informations sur votre Skype pour Business Online client, appeler la cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sans aucun paramètre supplémentaire.
  
```
Get-CsTenant
```

Pour retourner uniquement les clients nom et l’ID, utilisez cette commande.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

La valeur du paramètre _ID client sur_ est requise lors de l’exécution des applets de commande telles que [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) et [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).
  
Pour savoir si des informations de licence pour le client spécifié sont disponibles dans le Skype pour le centre d’administration Business en ligne, utilisez l’applet de commande [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>Voir aussi
[Configurer votre ordinateur pour Skype pour la gestion en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
