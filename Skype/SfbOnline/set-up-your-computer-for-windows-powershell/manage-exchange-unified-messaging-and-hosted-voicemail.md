---
title: Gérer la messagerie unifiée Exchange et la messagerie vocale hébergée
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
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
description: Utiliser PowerShell pour gérer les fonctionnalités de la messagerie unifiée Exchange tels que le standard automatique et accès abonné et messagerie vocale hébergée dans Skype pour Business Online.
ms.openlocfilehash: 10c1891272a81731c94e5f0f459bb91e532e8387
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849792"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Gérer la messagerie unifiée Exchange et la messagerie vocale hébergée

Vous pouvez gérer la messagerie unifiée Exchange et hébergez de la messagerie vocale dans Skype pour Business Online à l’aide d’un ensemble d’applets de commande.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Gérer la messagerie unifiée Exchange et hébergée par la messagerie vocale

Les applets de commande suivantes peuvent être utilisées pour gérer la messagerie unifiée Exchange (MU) et hébergée par les stratégies de messagerie vocale :
  
|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |Crée et gère les objets contacts utilisés pour les services de standard automatique et accès abonné, lors de la messagerie unifiée Exchange est un service hébergé.  <br/><br/> Skype pour Business Online fonctionne avec la messagerie unifiée Exchange pour fournir plusieurs fonctionnalités vocales, y compris l’accès abonné et standard automatique. Standard automatique fournit un moyen d’appels automatiquement une réponse et acheminé à la bonne personne. L’accès abonné permet aux utilisateurs de se connecter à la messagerie unifiée Exchange et extraire le courrier électronique, les messages vocaux, les contacts et les informations de calendrier.  <br/><br/> Lorsque la messagerie unifiée Exchange est fournie en tant que service hébergé, les objets contacts utilisés pour les services de standard automatique et accès abonné doivent être créés à l’aide de Microsoft PowerShell. Ces objets sont créés et gérés à l’aide des applets de commande **CsExUmContact** . <br/> |
|[Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |Gère les stratégies de messagerie vocale hébergée utilisées dans l’organisation. Stratégies de messagerie vocale hébergée spécifient comment sans réponse les appels sont routés vers le service de messagerie unifiée Exchange. Ces stratégies affectent uniquement les utilisateurs qui ont été activés pour la messagerie vocale de la messagerie unifiée Exchange hébergé.  <br/><br/> Pour vérifier si un utilisateur est activé pour la messagerie vocale hébergée, exécutez une commande semblable à ce qui suit à l’invite de PowerShell.  <br/> « Get-CsOnlineUser-Identity « kenmyer@litwareinc.com » | Select-Object HostedVoiceMail'|
   

## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour Skype pour la gestion en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 