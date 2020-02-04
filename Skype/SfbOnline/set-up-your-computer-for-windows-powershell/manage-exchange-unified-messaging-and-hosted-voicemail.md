---
title: Gérer la messagerie unifiée Exchange et la messagerie vocale hébergée
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
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
description: Utiliser PowerShell pour gérer les fonctionnalités de messagerie unifiée Exchange telles que le standard automatique et l’accès abonné et la boîte vocale hébergée dans Skype entreprise online.
ms.openlocfilehash: d0c2ff8cad705a2d00685e2c6935616ab8d64ac9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692679"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Gérer la messagerie unifiée Exchange et la messagerie vocale hébergée

Vous pouvez gérer la messagerie unifiée Exchange et la boîte vocale hébergée dans Skype entreprise Online à l’aide d’un ensemble d’applets de connexion.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Gestion de la messagerie unifiée Exchange et de la messagerie vocale hébergée

Les applets de commande suivantes permettent de gérer les stratégies de messagerie unifiée (MU) et de boîte vocale hébergées :
  

| **Applet de commande**                                                                                                                                                                                                                                                                                                                        | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | Permet de créer et de gérer les objets de contact utilisés pour le standard automatique et les services d’accès aux abonnés lorsque Exchange UM est un service hébergé.  <br/><br/> Skype entreprise Online fonctionne avec la messagerie unifiée Exchange pour fournir plusieurs fonctionnalités de voix, dont le standard automatique et l’accès abonné. Le standard automatique permet d’obtenir une réponse automatique aux appels et de les acheminer vers la personne concernée. L’accès des abonnés permet aux utilisateurs de se connecter à la messagerie unifiée Exchange et de récupérer le courrier électronique, les messages vocaux, les contacts et les informations de calendrier.  <br/><br/> Lorsque la messagerie unifiée Exchange est fournie en tant que service hébergé, les objets de contact utilisés pour le standard automatique et les services d’accès aux abonnés doivent être créés à l’aide de Microsoft PowerShell. Ces objets sont créés et gérés en utilisant les applets de applet de **CsExUmContact** . <br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | Gestion des stratégies de messagerie vocale hébergées utilisées dans l’organisation. Les stratégies de messagerie vocale hébergées spécifient le mode de routage des appels sans réponse au service de messagerie unifiée Exchange. Ces stratégies affectent uniquement les utilisateurs qui ont été activés pour la boîte vocale hébergée de messagerie unifiée Exchange.  <br/><br/> Pour vérifier si un utilisateur est activé pour la boîte vocale hébergée, exécutez une commande similaire à celle qui suit dans l’invite PowerShell.  <br/> \`Get-CsOnlineUser-Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour la gestion de Skype entreprise Online à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
