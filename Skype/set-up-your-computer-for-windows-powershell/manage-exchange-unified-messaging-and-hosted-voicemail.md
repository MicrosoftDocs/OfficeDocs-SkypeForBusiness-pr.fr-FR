---
title: "Gérer la messagerie unifiée Exchange et hébergé de messagerie vocale"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: "Utiliser PowerShell pour gérer des fonctionnalités de la messagerie unifiée Exchange telles que de Standard automatique et l’accès abonné et hébergé de messagerie vocale dans Skype pour l’activité en ligne."
ms.openlocfilehash: a5f358d06ed7c7e805aeffbce6a6898cc2a86b73
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Gérer la messagerie unifiée Exchange et hébergé de messagerie vocale

Vous pouvez gérer la messagerie unifiée Exchange et hébergé de messagerie vocale dans Skype pour entreprise en ligne à l’aide d’un jeu d’applets de commande.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Gérer la messagerie unifiée Exchange et hébergé de la messagerie vocale

Les applets de commande suivant peut être utilisé pour gérer la messagerie unifiée Exchange (MU) et hébergé des stratégies de messagerie vocale :
  
|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [Nouvelle-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Supprimer-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Ensemble-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |Crée et gère les objets de contact utilisés pour les services de Standard automatique et de l’accès abonné, lors de la messagerie unifiée Exchange est un service hébergé.  <br/><br/> Skype pour Business Online fonctionne avec la messagerie unifiée d’Exchange pour fournir plusieurs fonctionnalités liés à la voix, y compris de Standard automatique et de l’accès abonné. Standard automatique offre un moyen pour les appels automatiquement une réponse et acheminé à la bonne personne. L’accès abonné permet aux utilisateurs de se connecter à la messagerie unifiée d’Exchange et de récupérer des e-mail, les messages vocaux, les contacts et les informations de calendrier.  <br/><br/> Lorsque la messagerie unifiée Exchange est fourni sous la forme d’un service hébergé, les objets de contact utilisés pour les services de Standard automatique et de l’accès abonné doivent être créés à l’aide de Microsoft PowerShell. Ces objets sont créés et gérés à l’aide des applets de commande **CsExUmContact** . <br/> |
|[Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |Gère les stratégies de messagerie vocale hébergés utilisés dans l’organisation. Stratégies de messagerie vocale hébergés spécifient les appels en attente comment sont routés vers le service de messagerie unifiée Exchange. Ces stratégies affectent uniquement les utilisateurs qui ont été activés pour la messagerie unifiée Exchange hébergé de messagerie vocale.  <br/><br/> Pour vérifier si un utilisateur est activé pour la messagerie vocale hébergé, exécutez une commande semblable à la suivante à l’invite de PowerShell.  <br/> ' Get-CsOnlineUser-Identity « kenmyer@litwareinc.com » | Select-Object HostedVoiceMail'|
   

## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour Skype pour la gestion d’entreprise en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)