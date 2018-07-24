---
title: Partenaires fédérés de Skype Room System et Skype Entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Consultez cette rubrique pour obtenir plus d’informations sur la façon de configurer Skype Room System pour Skype Entreprise pour les entreprises partenaires fédérées.
ms.openlocfilehash: 8099b5af72d4ce8e5a8be25c7fabc8563387dd46
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997950"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Partenaires fédérés de Skype Room System et Skype Entreprise
 
Consultez cette rubrique pour obtenir plus d’informations sur la façon de configurer Skype Room System pour Skype Entreprise pour les entreprises partenaires fédérées.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Partenaires fédérés de Skype Room System et Skype Entreprise

Système de salle Skype repose sur la Skype joindre pour le lien de la réunion d’entreprise dans la demande de réunion du calendrier. Le lien de participation se trouve généralement dans le corps d’une demande de réunion. Toutefois, Skype salle système dépend de ce lien pour être présents dans les propriétés MAPI du message. Lorsque cette réunion est envoyée pour les organisations à distance (Skype pour les partenaires fédérés), par défaut sera Skype salle système de l’organisation distante pas la participation aux réunions lien dans le calendrier pour afficher. En fait, les utilisateurs d’Outlook dans l’organisation distante ne pourront pas participer à la Skype pour la réunion d’entreprise en un clic droit du calendrier, élément ou de dans le rappel de réunion. Ils doivent invitation à la réunion, cliquez sur Skype joindre pour Business réunion dans le corps du message. 
  
La raison de cette limitation est qu’Outlook et Microsoft Exchange n’utilisent pas de méthode spéciale pour regrouper des informations lorsque des messages sont envoyés sur Internet. Cette méthode, appelée format Transport Neutral Encapsulation (TNEF), est désactivée par défaut pour les messages d’une organisation Exchange envoyés en externe. Pour une réunion lien participer à une doit apparaître sur un système de salle Skype à distance, l’organisation émettrice doit activer TNEF à l’aide de la commande suivante :
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Après l’activation de la TNEF pour l’organisation, tous les messages envoyés sur Internet à l’organisation sont envoyés en tant que pièce jointe au format TNEF. Avec TNEF activé, lorsqu’un Skype pour une demande de réunion Business est envoyé à la Skype des partenaires fédérés, Skype salle système pourront restituer la jointure Skype pour une réunion d’affaires et les utilisateurs distants pourront participer à Skype pour les réunions d’entreprise. 