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
description: Utilisez PowerShell pour gérer les fonctionnalités de messagerie unifiée Exchange, telles que l’accès Standard automatique abonnés et l’accès aux abonnés et la messagerie vocale hébergée dans Skype Entreprise Online.
ms.openlocfilehash: 393b0a43cb55462006ef7701396a3b7840032fb4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113200"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Gérer la messagerie unifiée Exchange et la messagerie vocale hébergée

Vous pouvez gérer la messagerie unifiée Exchange et la messagerie vocale hébergée dans Skype Entreprise Online à l’aide d’un ensemble d’lets.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Gérer la messagerie unifiée Exchange et la messagerie vocale hébergée

Les cmdlets suivantes peuvent être utilisées pour gérer la messagerie unifiée Exchange (UM) et les stratégies de messagerie vocale hébergée :
  

| **Applet de commande**                                                                                                                                                                                                                                                                                                                        | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | Crée et gère les objets de contact utilisés pour les services Standard automatique et Subscriber Access, quand Exchange UM est un service hébergé.  <br/><br/> Skype Entreprise Online fonctionne avec exchange UM pour vous offrir plusieurs fonctionnalités vocales, notamment la messagerie Standard automatique et l’accès abonné. Standard automatique permet de répondre automatiquement aux appels et de les router vers la personne qui les appelle. L’Accès abonné permet aux utilisateurs de se connecter à exchange UM et de récupérer des messages, des messages vocaux, des contacts et des informations de calendrier.  <br/><br/> Lorsque exchange UM est fourni en tant que service hébergé, les objets de contact utilisés pour les services Standard automatique et Subscriber Access doivent être créés à l’aide de Microsoft PowerShell. Ces objets sont créés et gérés à l’aide des cmdlets **CsExUmContact.** <br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | Gère les stratégies de messagerie vocale hébergées utilisées dans l’organisation. Les stratégies de messagerie vocale hébergée spécifient la manière dont les appels sans réponse sont acheminés vers le service De messagerie un3 Exchange. Ces stratégies concernent uniquement les utilisateurs ayant été activés pour la messagerie vocale hébergée sur Exchange UM.  <br/><br/> Pour vérifier si un utilisateur est activé pour la messagerie vocale hébergée, exécutez une commande similaire à la suivante à partir de l’invite PowerShell.  <br/> \`Get-CsOnlineUser -Identity « kenmyer@litwareinc.com »                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
