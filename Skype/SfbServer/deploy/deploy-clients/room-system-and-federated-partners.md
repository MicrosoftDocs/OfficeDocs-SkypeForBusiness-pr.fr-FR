---
title: Skype Système de salle et Skype Entreprise partenaires fédérés
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lisez cette rubrique pour découvrir comment configurer Skype Room System pour Skype Entreprise partenaires fédérés.
ms.openlocfilehash: ee9d7013df141cfe937f1c006a5e659a9e8a7478
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841936"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Système de salle et Skype Entreprise partenaires fédérés
 
Lisez cette rubrique pour découvrir comment configurer Skype Room System pour Skype Entreprise partenaires fédérés.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Système de salle et Skype Entreprise partenaires fédérés

Skype Le système de salle s’appuie sur le lien Skype Entreprise réunion dans la demande de réunion du calendrier. Le lien de connexion se trouve généralement dans le corps d’une demande de réunion. Toutefois, Skype Room System dépend de ce lien pour être présent dans les propriétés MAPI du message. Lorsque cette demande de réunion est envoyée à des organisations distantes (partenaires fédérés Skype Entreprise), par défaut le système Skype Room de l’organisation distante n’affiche pas le lien de la réunion dans le calendrier. En fait, les Outlook utilisateurs de l’organisation distante ne pourront pas participer à la réunion Skype Entreprise en cliquant avec le bouton droit sur l’élément de calendrier ou à partir du rappel de réunion. Ils doivent ouvrir l’invitation à la réunion et cliquer sur Rejoindre Skype Entreprise réunion dans le corps du message. 
  
La raison de cette limitation est que Outlook et Microsoft Exchange n’utilisent pas de méthode spéciale pour mettre en package des informations pour l’envoi de messages sur Internet. Cette méthode, appelée TNEF (Transport Neutral Encapsulation Format), est désactivée par défaut pour les messages envoyés en externe à partir d’Exchange organisation. Pour qu’un lien de rejoindre une réunion apparaisse sur un système Skype salle distant, l’organisation d’envoi doit activer le TNEF à l’aide de la commande suivante :
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Une fois le format TNEF activé pour l’organisation distante, tout message envoyé via Internet à l’organisation est envoyé en tant que pièce jointe au format TNEF. Avec le TNEF activé, lorsqu’une demande de réunion Skype Entreprise est envoyée au partenaire fédéré Skype Entreprise, Skype Room System peut restituer la réunion de Skype Entreprise et les utilisateurs distants peuvent participer à des réunions Skype Entreprise. 
