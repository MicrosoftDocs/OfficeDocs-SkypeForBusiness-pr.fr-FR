---
title: "Gérer Skype pour les entreprises commerciales en ligne"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: "Utiliser Windows PowerShell et les applets de commande Get-CsTenant et Get-CsTenantLicensingConfiguration pour obtenir des informations sur votre Skype pour clients d’entreprise en ligne."
ms.openlocfilehash: 6461a15baeed3bf3fde0ee79dc24f7863eaabd02
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/27/2018
---
# <a name="manage-skype-for-business-online-organizations"></a>Gérer Skype pour les entreprises commerciales en ligne

Vous trouverez des informations sur votre Skype pour clients d’entreprise en ligne à l’aide des applets de commande **Get-CsTenant** et **Get-CsTenantLicensingConfiguration** .
  
## <a name="manage-skype-for-business-online-tenants"></a>Gérer Skype pour locataires Business en ligne

Pour retourner des informations sur votre Skype pour clients d’entreprise en ligne, appelez l’applet de commande [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sans paramètres supplémentaires.
  
```
Get-CsTenant
```

Pour retourner uniquement les clients nom et ID, utilisez cette commande.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

La valeur du paramètre _TenantID_ est obligatoire lors de l’exécution d’applets de commande [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) des [CsTenantFederationConfiguration de l’ensemble](https://technet.microsoft.com/en-us/library/jj994080.aspx).
  
Pour savoir si les informations de licence pour le client spécifié sont disponibles dans le Skype pour Business Online Centre d’administration, utilisez l’applet de commande [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour Skype pour la gestion d’entreprise en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

## <a name="feedback"></a>Commentaires ?
Pour fournir des commentaires sur le produit ou pour nous faire savoir comment nous faisons, consultez [Skype pour les commentaires de l’entreprise](https://www.skypefeedback.com).