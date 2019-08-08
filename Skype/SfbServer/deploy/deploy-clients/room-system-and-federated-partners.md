---
title: Partenaires fédérés de Skype Room System et Skype Entreprise
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Consultez cette rubrique pour obtenir plus d’informations sur la façon de configurer Skype Room System pour Skype Entreprise pour les entreprises partenaires fédérées.
ms.openlocfilehash: a3f7841ab3e04220c0b6d77a5f2e3605d3ac6e67
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235044"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Partenaires fédérés de Skype Room System et Skype Entreprise
 
Consultez cette rubrique pour obtenir plus d’informations sur la façon de configurer Skype Room System pour Skype Entreprise pour les entreprises partenaires fédérées.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Partenaires fédérés de Skype Room System et Skype Entreprise

Le système de salle Skype repose sur le lien participer à une réunion Skype entreprise dans la demande de réunion du calendrier. Le lien de participation se trouve généralement dans le corps d’une demande de réunion. En revanche, le système de salle Skype dépend du lien que vous souhaitez présenter dans les propriétés MAPI du message. Lorsque cette demande de réunion est envoyée à des organisations distantes (partenaires fédérés Skype entreprise), par défaut, le système de salle Skype de l’organisation distante ne montre pas le lien de participation à la réunion dans le calendrier. En fait, les utilisateurs Outlook de l’organisation à distance ne seront pas en mesure de rejoindre la réunion Skype entreprise en cliquant avec le bouton droit sur l’élément de calendrier ou à partir du rappel de réunion. Elle doit ouvrir l’invitation à la réunion et cliquer sur participer à une réunion Skype entreprise dans le corps du message. 
  
La raison de cette limitation est qu’Outlook et Microsoft Exchange n’utilisent pas de méthode spéciale pour regrouper des informations lorsque des messages sont envoyés sur Internet. Cette méthode, appelée format Transport Neutral Encapsulation (TNEF), est désactivée par défaut pour les messages d’une organisation Exchange envoyés en externe. Pour qu’un lien de participation à une réunion apparaisse dans un système de salle Skype distant, l’organisation d’expédition doit activer TNEF en utilisant la commande suivante:
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Après l’activation de la TNEF pour l’organisation, tous les messages envoyés sur Internet à l’organisation sont envoyés en tant que pièce jointe au format TNEF. Lorsque TNEF est activé, lors de l’envoi d’une demande de réunion Skype entreprise au partenaire fédéré Skype entreprise, le système de salle Skype est en mesure d’effectuer la participation à une réunion Skype entreprise et les utilisateurs distants pourront participer à des réunions Skype entreprise. 
