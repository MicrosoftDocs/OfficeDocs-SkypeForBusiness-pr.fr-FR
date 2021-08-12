---
title: Skype Système de salle et partenaires Skype Entreprise fédérés
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lisez cette rubrique pour découvrir comment configurer Skype Room System pour Skype Entreprise partenaires fédérés.
ms.openlocfilehash: ba31d945425c2f5e32bc09e6b97c6204e492f414b5ca6b2e5ceaf3e65d0de3be
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294911"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Système de salle et partenaires Skype Entreprise fédérés
 
Lisez cette rubrique pour découvrir comment configurer Skype Room System pour Skype Entreprise partenaires fédérés.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Système de salle et partenaires Skype Entreprise fédérés

Skype Le système de salle s’appuie sur le lien Skype Entreprise réunion dans la demande de réunion du calendrier. Le lien de connexion se trouve généralement dans le corps d’une demande de réunion. Toutefois, Skype Room System dépend de ce lien pour être présent dans les propriétés MAPI du message. Lorsque cette demande de réunion est envoyée à des organisations distantes (partenaires fédérés Skype Entreprise), par défaut le système Skype Room de l’organisation distante n’affiche pas le lien de la réunion dans le calendrier. En fait, les Outlook utilisateurs de l’organisation distante ne pourront pas participer à la réunion Skype Entreprise en cliquant avec le bouton droit sur l’élément de calendrier ou à partir du rappel de réunion. Ils doivent ouvrir l’invitation à la réunion et cliquer sur Rejoindre Skype Entreprise réunion dans le corps du message. 
  
La raison de cette limitation est que Outlook et Microsoft Exchange n’utilisent pas de méthode spéciale pour mettre en package des informations pour l’envoi de messages sur Internet. Cette méthode, appelée TNEF (Transport Neutral Encapsulation Format), est désactivée par défaut pour les messages envoyés en externe à partir d’Exchange organisation. Pour qu’un lien de rejoindre une réunion apparaisse sur un système Skype salle distant, l’organisation d’envoi doit activer le TNEF à l’aide de la commande suivante :
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Une fois le format TNEF activé pour l’organisation distante, tout message envoyé via Internet à l’organisation est envoyé en tant que pièce jointe au format TNEF. Avec le TNEF activé, lorsqu’une demande de réunion Skype Entreprise est envoyée au partenaire fédéré Skype Entreprise, Skype Room System peut restituer la réunion de Skype Entreprise et les utilisateurs distants peuvent participer à des réunions Skype Entreprise. 
