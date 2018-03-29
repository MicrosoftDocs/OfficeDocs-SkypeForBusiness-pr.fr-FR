---
title: Partenaires fédérés de Skype Room System et Skype Entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Consultez cette rubrique pour obtenir plus d’informations sur la façon de configurer Skype Room System pour Skype Entreprise pour les entreprises partenaires fédérées.
ms.openlocfilehash: 040af495217217b3bfd10fb577b7194df354e027
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Partenaires fédérés de Skype Room System et Skype Entreprise
 
Consultez cette rubrique pour obtenir plus d’informations sur la façon de configurer Skype Room System pour Skype Entreprise pour les entreprises partenaires fédérées.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Partenaires fédérés de Skype Room System et Skype Entreprise

Système de chambre de Skype s’appuie sur le Skype joindre pour le lien de réunion d’affaires dans la demande de réunion du calendrier. Le lien de participation se trouve généralement dans le corps d’une demande de réunion. Toutefois, Skype espace système dépend de ce lien dans les propriétés du message MAPI. Lors de cette réunion est envoyée aux organisations à distance (Skype pour partenaires fédérés), par défaut ne de Skype espace système de l’organisation à distance affiche pas lier de la jointure de la réunion dans le calendrier. En fait, tous les utilisateurs d’Outlook de l’organisation à distance ne pourront pas participer à la Skype pour une réunion d’affaires avec un clic droit du calendrier article ou à partir de dans le rappel de réunion. Ils doivent ouvrir l’invitation à une réunion et cliquez sur Joindre un Skype pour une réunion d’affaires dans le corps du message. 
  
La raison de cette limitation est qu’Outlook et Microsoft Exchange n’utilisent pas de méthode spéciale pour regrouper des informations lorsque des messages sont envoyés sur Internet. Cette méthode, appelée format Transport Neutral Encapsulation (TNEF), est désactivée par défaut pour les messages d’une organisation Exchange envoyés en externe. Pour une réunion lien de jointure doit apparaître sur un système distant salle de Skype, l’organisation émettrice doit activer TNEF à l’aide de la commande suivante :
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Après l’activation de la TNEF pour l’organisation, tous les messages envoyés sur Internet à l’organisation sont envoyés en tant que pièce jointe au format TNEF. Avec le format TNEF est activée, lorsqu’un Skype pour entreprise demande de réunion envoyée à la Skype des partenaires fédérés, Skype espace système pourront rendre la jointure Skype pour une réunion d’affaires et les utilisateurs distants pourront joindre Skype pour les réunions d’entreprise. 