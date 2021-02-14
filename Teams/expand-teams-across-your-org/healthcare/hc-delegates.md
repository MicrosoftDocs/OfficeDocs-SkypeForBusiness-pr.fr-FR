---
title: Délégation de messages
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Découvrez comment un utilisateur ayant le statut Absent(e) ou Ne pas déranger peut définir explicitement un autre utilisateur comme délégué dans son message d’état.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790466"
---
# <a name="message-delegation"></a>Délégation de messages

Un utilisateur peut déjà définir explicitement son statut sur Absent(0) ou Ne pas déranger et fournir un texte personnalisé. La fonctionnalité de délégation de message fonctionne comme suit :

1. Un utilisateur @username mentionne un autre utilisateur dans une partie d’un message texte, ce qui suggère que, bien qu’indisponibles, les personnes qui souhaitent les contacter à la place contactent l'@username utilisateur mentionné.
2. La personne désignée comme délégué est notifiée qu’elle a été désignée comme délégué.
3. Une personne qui essaie de contacter le premier utilisateur peut ensuite pointer sur le délégué désigné et envoyer facilement un message au délégué.  

Il s’agit d’un processus initié par l’utilisateur dans le client, et aucune implication de l’administrateur n’est requise pour activer la fonctionnalité. 

## <a name="delegation-use-scenario-in-healthcare"></a>Scénario d’utilisation de la délégation dans les soins de santé

*Exemple d’utilisation sans définir de délégués :*  Le dr.Nt Piccio est en appel au service de radiologye. Il reçoit un appel personnel urgent et doit s’éloigner pour les prochaines heures. Il demande à l’un de ses pairs du service de radioologie, Dr. Lena Ehrle, de le couvrir pendant son absence. Il place son pager à l’ami ami. Ehrle, qui est à l’écoute des messages urgents et des appels ping sur le pageur, et qui y répond au nom du Dr. Piccio, en plus de ses responsabilités actuelles. D’autres membres de l’équipe peuvent ne pas se rendre compte du fait que la délégation informelle s’est produite, et une confusion se produit avec les soins d’un patient.

*Exemple d’utilisation avec définition de délégués :* Le dr.Nt Piccio est en appel au service de radiologye. Il reçoit un appel personnel urgent et doit s’éloigner pour les prochaines heures. Il demande à l’un de ses pairs du service de radiologye, Dr. Lena Ehrle, de le couvrir pendant son absence. Il modifie son message de statut personnalisé pour dire quelque chose de similaire à « Je ne suis pas disponible pour les prochaines heures. Contactez le @DrEhrle pour toute urgence ».  D’autres membres de l’équipe réalisent que la délégation s’est produite alors qu’ils tentent de contacter le dr Piccio. Ils savent maintenant contacter le dr Ehrle en attendant. Il n’y a pas de confusion entre les soins d’un patient et peu à peu de confusion.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impact des modes de co-existence sur l’état de l’utilisateur dans le client Teams

Les administrateurs doivent savoir que les remarques d’état et les comportements de mention de délégation dépendent en partie du mode de co-existence d’un utilisateur. Cette matrice présente les possibilités :

|mode Co-Existence'écran | Comportement attendu|
|---|---|
|TeamsOnly |Les utilisateurs peuvent uniquement définir une note à partir de Teams. <br> La note Teams de l’utilisateur est visible dans Teams & SfB. |
|Île | Le jeu de notes de l’utilisateur dans Teams est visible uniquement dans Teams. <br> Note de l’utilisateur définie en SfB visible uniquement dans SfB |
|Modes SfB* | Les utilisateurs peuvent uniquement définir une note à partir de SfB. <br> La note SfB de l’utilisateur est visible dans SfB & Teams.  |
|||

Un utilisateur peut uniquement définir une note dans Teams si son mode est TeamsOnly ou Islands.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Affichage de notes définies dans Skype Entreprise
  
Aucune indication visuelle n’indique qu’une note a été définie à partir de Skype Entreprise.

Skype Entreprise n’applique pas de limite de caractères aux notes de statut. Microsoft Teams n’affiche que les 280 premiers caractères d’un jeu de notes à partir de Skype Entreprise. Une ellipse (...) à la fin d’une note indique une troncation.
  
Skype Entreprise ne prend pas en charge les heures d’expiration des notes.

La migration des notes de Skype Entreprise vers Teams n’est pas prise en charge lors de la mise à niveau d’un utilisateur vers le mode TeamsOnly.

## <a name="related-topics"></a>Sujets associés

[Coexistence avec Skype Entreprise](../../coexistence-chat-calls-presence.md)
