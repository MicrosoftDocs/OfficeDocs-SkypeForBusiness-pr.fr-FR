---
title: Partenaires fédérés Skype Room System et Skype Entreprise
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
description: Lisez cette rubrique pour découvrir comment configurer Skype Room System pour les partenaires fédérés Skype Entreprise.
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820804"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Partenaires fédérés Skype Room System et Skype Entreprise
 
Lisez cette rubrique pour découvrir comment configurer Skype Room System pour les partenaires fédérés Skype Entreprise.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Partenaires fédérés Skype Room System et Skype Entreprise

Skype Room System s’appuie sur le lien Participer à une réunion Skype Entreprise dans la demande de réunion de calendrier. Le lien de connexion se trouve généralement dans le corps d’une demande de réunion. Toutefois, Skype Room System dépend de ce lien pour être présent dans les propriétés MAPI du message. Lorsque cette demande de réunion est envoyée à des organisations distantes (partenaires fédérés Skype Entreprise), par défaut le système Skype Room de l’organisation distante n’affiche pas le lien de la réunion dans le calendrier. En fait, tous les utilisateurs Outlook de l’organisation distante ne pourront pas participer à la réunion Skype Entreprise en cliquant avec le bouton droit sur l’élément de calendrier ou à partir du rappel de réunion. Ils doivent ouvrir l’invitation à une réunion et cliquer sur Participer à une réunion Skype Entreprise dans le corps du message. 
  
La raison de cette limitation est qu’Outlook et Microsoft Exchange n’utilisent pas de méthode spéciale pour mettre en package des informations pour l’envoi de messages sur Internet. Cette méthode, appelée TNEF (Transport Neutral Encapsulation Format), est désactivée par défaut pour les messages envoyés en externe à partir d’une organisation Exchange. Pour qu’un lien de rejoindre une réunion apparaisse sur un système Skype Room distant, l’organisation d’envoi doit activer le TNEF à l’aide de la commande suivante :
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Une fois le format TNEF activé pour l’organisation distante, tout message envoyé via Internet à l’organisation est envoyé en tant que pièce jointe au format TNEF. Avec le TNEF activé, lorsqu’une demande de réunion Skype Entreprise est envoyée au partenaire fédéré Skype Entreprise, Skype Room System peut restituer la réunion Skype Entreprise et les utilisateurs distants peuvent participer aux réunions Skype Entreprise. 
