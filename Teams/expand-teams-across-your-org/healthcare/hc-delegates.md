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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Découvrez comment un utilisateur ayant le statut Absent ou Ne pas déranger peut définir explicitement un autre utilisateur en tant que délégué dans son message d’état.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 14f58861074ed8b9291ca725f60ff1612534f4dc
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674206"
---
# <a name="message-delegation"></a>Délégation de messages

Un utilisateur peut déjà définir explicitement son statut sur Absent(s) ou Ne pas déranger, et fournir un texte personnalisé. La fonctionnalité de délégation de message fonctionne comme suit :

1. Un utilisateur @username mentionne un autre utilisateur dans une partie d'un message d'état textuel, suggérant que pendant qu'ils sont indisponibles, les personnes qui veulent les contacter doivent plutôt contacter l'utilisateur mentionné @username.
2. La personne qui a été désignée comme déléguée est informée qu'elle a été désignée pour être déléguée.
3. Une personne qui tente de contacter le premier utilisateur peut alors passer la souris sur le délégué désigné et lui envoyer un message.  

Il s’agit d’un processus initié par l’utilisateur dans le client. Aucune implication de l’administrateur n’est nécessaire pour activer la fonctionnalité. 

## <a name="delegation-use-scenario-in-healthcare"></a>Scénario d'utilisation de la délégation dans le secteur des soins de santé

*Exemple d’utilisation sans définition de délégués :*  Le Dr Franco Piccio est de garde au service de radiologie. Il reçoit un appel personnel urgent et doit s’absenter pendant les prochaines heures. Il demande à l'une de ses collègues du service de radiologie, le Dr Lena Ehrle, de le remplacer pendant son absence. Il remet officieusement son téléavertisseur au Dr Ehrle, qui est à l'écoute des messages urgents et des bips sur le téléavertisseur et y répond au nom du Dr Piccio en plus de ses responsabilités actuelles. Les autres membres de l'équipe peuvent ne pas se rendre compte que la délégation informelle a eu lieu, et il s'ensuit une confusion dans les soins prodigués au patient.

*Exemple d’utilisation avec définition de délégués :* Le Dr Franco Piccio est de garde au service de radiologie. Il reçoit un appel personnel urgent et doit s’absenter pendant les prochaines heures. Il demande à l'une de ses collègues du service de radiologie, le Dr Lena Ehrle de le remplacer pendant son absence. Il modifie son message d’état personnalisé de façon à dire « Je ne suis pas disponible pendant les prochaines heures. Veuillez contacter le @DrEhrle en cas d’urgence. »  Les autres membres de l'équipe réalisent que la délégation s'est produite alors qu'ils tentaient de contacter le Dr Piccio. Ils savent donc qu'ils doivent contacter le Dr Ehrle en attendant. Il y a peu ou pas de confusion dans les soins prodigués au patient.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impact des modes de coexistence sur le statut de l'utilisateur dans le client Teams

Les administrateurs doivent savoir que le comportement des notes d'état et des mentions de délégation dépendra en partie du mode de coexistence de l'utilisateur. Cette matrice affiche les possibilités qui s’offrent à vous :

|Mode de coexistence | Comportement attendu|
|---|---|
|TeamsOnly |Les utilisateurs peuvent définir une note à partir de Teams uniquement. <br> La note Teams de l’utilisateur est visible dans Teams & SfB. |
|Île | Le jeu de notes de l’utilisateur dans Teams n’est visible que dans Teams. <br> Le jeu de notes de l’utilisateur dans SfB n’est visible que dans SfB. |
|Modes SfB* | Les utilisateurs peuvent définir une note à partir de SfB uniquement. <br> La note SfB de l’utilisateur est visible dans SfB & Teams.  |
|||

Un utilisateur peut seulement définir une note dans Teams si son mode est TeamsOnly ou Îles.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Affichage de notes définies dans Skype Entreprise
  
Il n’existe aucune indication visuelle qu’une note a été définie à partir de Skype Entreprise.

Skype Entreprise n’applique pas une limite de caractères aux notes d’état. Microsoft Teams affiche uniquement les 280 premiers caractères d’un jeu de notes à partir de Skype Entreprise. Une ellipse (...) à la fin d’une note indique une troncation.
  
Skype Entreprise ne prend pas en charge les délais d’expiration des notes.

La migration des notes de Skype Entreprise vers Teams n’est pas prise en charge lorsqu’un utilisateur est mis à niveau vers le mode TeamsOnly.

## <a name="related-topics"></a>Rubriques connexes

[Coexistence avec Skype Entreprise](../../coexistence-chat-calls-presence.md)
