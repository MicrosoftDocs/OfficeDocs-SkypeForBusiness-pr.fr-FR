---
title: Répondre de standard automatique et appels de file d’attente directement à partir d’équipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: article
ms.service: msteams
description: Décrit les standards automatiques de système téléphonique et les files d’attente de l’appel et explique comment vous pouvez répondre à ces appels dans les équipes.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b0b533020def2e344991fa758304888c8166436
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839204"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Répondre de standard automatique et appels de file d’attente directement à partir d’équipes
===========================================================

Les utilisateurs des équipes peuvent recevoir et répondez aux appels depuis Skype pour Business Online standard automatique et files d’attente des appels directement à partir du client de leurs équipes. Pour les utilisateurs d’équipes, la fonctionnalité de standard automatique est désormais disponible et la fonctionnalité de file d’attente d’appel est en mode Aperçu. 

## <a name="what-are-auto-attendants-and-call-queues"></a>Que sont les standards automatiques et files d’attente des appels ?

Standards automatiques de système téléphonique fournissent une série d’invites vocales ou un fichier audio que les appelants entendront au lieu d’un opérateur humain quand ils appellent vers une organisation. Un standard automatique permet aux utilisateurs de parcourir le système de menu, de passer des appels ou de rechercher des utilisateurs en utilisant un clavier téléphonique (DTMF) ou effectuer des entrées vocales à l'aide de la reconnaissance vocale.

Appel de système téléphonique files d’attente contiennent le message d’accueil qui est utilisés lorsqu’une personne appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la capacité de recherche pour l’agent disponible appel suivant gérer l’appel pendant les personnes qui appel Écoutez une musique d’attente. Vous pouvez créer une seule ligne ou plusieurs files d’attente d’appel pour votre organisation.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Gestion d’un appel de file d’attente standard ou un appel automatique

Les utilisateurs pourront différencier les appels entrants à partir d’une file d’attente automatique standard ou un appel avant de prendre l’appel. Ainsi que le nom et/ou le numéro de l’appelant, chaque appel inclut des informations sur qui l’appelant a essayé d’atteindre, offrant aux utilisateurs un meilleur contexte pour le traitement de l’appelant.

L’illustration suivante montre l’apparence d’un appel entrant à partir d’une file d’attente automatique standard ou un appel à un utilisateur.

![Notification d’appel entrant](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Une fois que la réponse à un appel de file d’attente automatique standard ou un appel, l’utilisateur peut traiter l’appel comme n’importe quel autre appel & #x 2014 ; ils peuvent ajouter ou conférence dans un autre utilisateur ou transférer l’appel vers une autre partie. En outre, les appels standard automatique seront transférés en fonction de la configuration de l’utilisateur.

> [!NOTE] 
> File d’attente d’appel n’est pas transférés en fonction de la configuration de l’utilisateur. Afin de garantir les appelants restent dans la file d’attente jusqu'à ce qu’un agent peut répondre à l’appel et l’appelant n’est pas transféré de manière inattendue.

## <a name="supported-clients"></a>Clients pris en charge

Prise en charge pour les appels de file d’attente standard et appel automatique est disponible dans les clients suivants :

-   Client Microsoft Teams Windows (versions 32 et 64 bits)
-   Client Mac Microsoft Teams
-   Application iPhone Microsoft Teams
-   Application Android Microsoft Teams

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurer le support de file d’attente des standard et appel automatique pour Microsoft Teams

Pour recevoir le standard automatique et appels de file d’attente sur Microsoft Teams, vous devez configurer votre stratégie d’interopérabilité et mise à niveau de stratégie. Examinez la [Migration et interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises](migration-interop-guidance-for-teams-with-skype.md). Si vous n’avez pas de standard automatique ou la file d’attente d’appel configuré et qu’il souhaite faire, voir [définir un standard automatique de système téléphonique](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) et [créer une file d’attente des appels système téléphonique](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

## <a name="related-topics"></a>Rubriques connexes

-   [Quel est le système téléphonique dans Office 365](what-is-phone-system-in-office-365.md)
-   [Créer une file d’attente de système téléphonique](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [Que sont les standards automatiques de système téléphonique ?](what-are-phone-system-auto-attendants.md)
-   [Configurer un standard automatique pour le système téléphonique](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

