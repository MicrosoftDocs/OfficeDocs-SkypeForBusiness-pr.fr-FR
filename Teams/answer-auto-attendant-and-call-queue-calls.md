---
title: Répondre aux appels du attendant automatique et de la file d’attente d’appels
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Décrit les files d’attente et les files d’attente automatiques dans le cloud, et explique comment vous pouvez répondre à ces appels dans Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cca068ab1194a48eb775550e4bf3f99826d82d2a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874664"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Répondre aux appels dans la file d’attente ou du standard automatique directement à partir de Teams
===========================================================

Les utilisateurs de Teams peuvent recevoir et recevoir des appels à partir de attendants automatiques cloud et de files d’attente d’appels directement à partir de leur client Teams.

## <a name="what-are-auto-attendants-and-call-queues"></a>Que sont les files d’attente et les files d’attente automatiques ?

Les serveurs automatiques cloud fournissent une série d’invites vocales ou un fichier audio que les appelants entendent au lieu d’un opérateur lorsqu’ils appellent une organisation. Un standard automatique permet aux utilisateurs de parcourir le système de menu, de passer des appels ou de rechercher des utilisateurs en utilisant un clavier téléphonique (DTMF) ou effectuer des entrées vocales à l'aide de la reconnaissance vocale.

Les files d’attente d’appels cloud incluent des salutations qui sont utilisées lorsque quelqu’un appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel pendant que l’appelant écoute la musique mise en attente. Vous pouvez créer une ou plusieurs files d’attente pour votre organisation.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Gestion d’un traitement automatique ou d’un appel de la file d’attente d’appels

Les utilisateurs pourront différencier les appels entrants à partir d’un traitement automatique ou d’une file d’attente d’appels avant de répondre à l’appel. En plus du nom et/ou du numéro de l’appelant, chaque appel inclut des informations sur les personnes que l’appelant essayait de joindre, afin de donner aux utilisateurs un meilleur contexte pour s’adresser à l’appelant.

L’illustration suivante montre comment un appel entrant d’un employé de service automatique ou d’une file d’attente d’appels s’affiche pour un utilisateur.

![Capture d’écran d’une notification d’appel entrant](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Une fois qu’un attendant automatique ou un appel de la file d’attente d’appels a été reçu, l’utilisateur peut traiter l’appel comme n’importe quel autre &#x2014; il peut ajouter ou conférencer dans un autre utilisateur ou transférer l’appel à une autre partie. Par ailleurs, les appels du attendant automatique seront transmis en fonction de la configuration de l’utilisateur.

> [!NOTE] 
> Les appels de la file d’attente ne sont pas transmis en fonction de la configuration de l’utilisateur. Ceci permet de s’assurer que les appelants restent dans la file d’attente jusqu’à ce qu’un agent puisse répondre à l’appel et que l’appelant ne soit pas transmis de manière inattendue.

> Les agents sont informés des appels manqués ou des messages vocaux pour les appels de la file d’attente d’appels.

## <a name="supported-clients"></a>Clients pris en charge

La prise en charge du service de support automatique et des appels en file d’attente est disponible dans les clients suivants :

-    Client Windows Microsoft Teams (versions 32 et 64 bits)
-    Client Microsoft Teams Mac
-    Application Microsoft Teams pour iPhone
-    Application Microsoft Teams pour Android

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurer le support de la file d’attente automatique et du support des files d’attente pour Microsoft Teams

Pour recevoir des appels de attendant automatique et de file d’attente sur Microsoft Teams, vous devez configurer votre stratégie d’interopérabilité et de mise à niveau. Consultez la [migration et l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise.](migration-interop-guidance-for-teams-with-skype.md) Si vous n’avez pas de attendant automatique et/ou de file d’attente d’appels configuré et souhaitez le faire, consultez Configurer un attendant [automatique](create-a-phone-system-auto-attendant.md) cloud et Créer une file d’attente d’appels [cloud.](create-a-phone-system-call-queue.md)

## <a name="known-issues"></a>Problèmes connus

Lorsqu’un agent de la file d’attente d’appels reçoit un appel sur son appareil mobile, les appels peuvent être mis en attente si l’appareil est verrouillé. L’utilisateur doit tout d’abord déverrouiller l’appareil, puis répondre à l’appel.


## <a name="related-topics"></a>Rubriques connexes

-    [Qu’est-ce que Phone System dans Microsoft 365 ou Office 365 ?](what-is-phone-system-in-office-365.md)
-    [Créer une file d’attente d’appels cloud](create-a-phone-system-call-queue.md)
-    [Un standard Cloud automatique, qu’est-ce que c’est ?](what-are-phone-system-auto-attendants.md)
-    [Configurer un standard automatique dans le cloud](create-a-phone-system-auto-attendant.md)

