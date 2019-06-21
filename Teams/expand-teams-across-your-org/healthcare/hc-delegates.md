---
title: Délégation de message
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Un utilisateur peut définir explicitement un autre utilisateur comme délégué dans son message d’État.
ms.openlocfilehash: be7092d2a68010d00a2d214f12bfe9011d44bbc5
ms.sourcegitcommit: 1786d4beccc8749e20709d2360d90e2bf7634925
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2019
ms.locfileid: "35119483"
---
# <a name="set-a-delegate-in-a-status-message"></a>Définir un délégué dans un message de statut

Un utilisateur peut déjà définir son état sur absent (e) ou ne pas déranger, et fournir un texte personnalisé. La fonctionnalité de délégation lui permet de @username mentionner un autre utilisateur dans le cadre d’un message de statut de texte, et de suggérer qu’il ne s’agit pas de personnes indisponibles pour le contacter en contactant plutôt le @username utilisateur mentionné. Une personne qui tente de vous contacter peut alors pointer sur le délégué désigné et le message facilement.  La personne qui a été désignée comme délégué est avertie qu’elle a été désignée comme délégué.

Il s’agit d’un processus initialisé par l’utilisateur dans le client et aucune implication d’administrateur n’est requise.

## <a name="delegation-use-scenario-in-healthcare"></a>Scénario d’utilisation de délégation dans la santé

*Exemple d’utilisation sans définir de délégués:*  Dr. Franco Piccio est en communication téléphonique au service de radiologie. Il reçoit un appel individuel urgent et doit s’éloigner pendant quelques heures. Il demande à l’un de ses homologues du service de radiologie, Dr. Lena Ehrle, de s’en informer pendant qu’il a disparu. Il a émis par le biais de son radiomessagerie pour le Dr. Ehrle, qui écoute les messages urgents et les télécommandes sur le téléavertisseur et y réponde au nom de Dr. Piccio en plus de ses responsabilités actuelles. Les autres membres de l’équipe risquent de ne pas se rendre compte que la délégation informelle s’est déroulée et que le prêt est en conflit avec le patient.

*Exemple d’utilisation avec de définir des délégués:* Dr. Franco Piccio est en communication téléphonique au service de radiologie. Il reçoit un appel individuel urgent et doit s’éloigner pendant quelques heures. Il demande l’un de ses pairs au service de radiologie, le Dr. Lena Ehrle pour s’en informer pendant qu’il a disparu. Il change son message de statut personnalisé pour qu’il ressemble à ce qui suit: «je ne suis pas disponible pendant quelques heures. Veuillez contacter @DrEhrle pour toute urgence.»  Les autres membres de l’équipe peuvent être conscients que la délégation s’est produite lors de la tentative de contact de la fonction de Piccio. Le léger risque de confusion avec les soins d’un patient.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impact des modes de coexistence sur l’état de l’utilisateur dans le client teams

Les administrateurs doivent savoir que les notes d’État et les mentions de délégation dépendent en partie du mode de coexistence d’un utilisateur. Ce tableau présente les possibilités suivantes:

|Mode de coexistence | Comportement attendu|
|---|---|
|TeamsOnly |Les utilisateurs peuvent définir une note uniquement dans Teams. <br> La note équipes de l’utilisateur est visible dans équipes & marketing. |
|Archipels | Remarque définie par l’utilisateur dans équipes uniquement visible dans Teams. <br> Note définie par l’utilisateur dans marketing visible uniquement dans marketing |
|Modes marketing * | Les utilisateurs peuvent définir une note uniquement à partir de marketing. <br> La note marketing de l’utilisateur est visible dans marketing & Teams.  |
|||

Un utilisateur peut uniquement définir une note dans teams s’il s’agit du mode TeamsOnly ou îlots.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Affichage de notes dans Skype entreprise
  
Il n’y a pas d’indications visuelles indiquant qu’une note a été définie dans Skype entreprise.

Skype entreprise n’applique aucune limite de caractères aux notes de statut. Microsoft teams n’affiche que les 280 premiers caractères d’un ensemble de notes dans Skype entreprise. Une ellipse (...) à la fin indique une troncature.
  
Skype entreprise ne prend pas en charge les délais d’expiration des notes.

La migration de notes de Skype entreprise vers teams n’est pas prise en charge lorsque l’utilisateur a procédé à la mise à niveau vers le mode TeamsOnly.

## <a name="configure-allowing-clients-to-use-delegates"></a>Configurer la possibilité pour les clients d’utiliser des délégués

Cette fonctionnalité ne nécessite pas de configuration dans le centre d’administration Microsoft teams ou à l’aide de PowerShell. Dans les clients qui la prennent en charge, il est disponible par défaut dans le client Teams.

## <a name="related-topics"></a>Voir aussi

[Coexistence avec Skype Entreprise](../../coexistence-chat-calls-presence.md)
