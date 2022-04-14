---
title: Répondre aux appels de standard automatique et de file d’attente d’appels
ms.reviewer: colongma
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Décrit les standards automatiques cloud et les files d’attente d’appels, et explique comment répondre à ces appels dans Teams.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 595be9303c0d9732c3e2580b06bf3a0a55a27088
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853075"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Répondre aux appels dans la file d’attente ou du standard automatique directement à partir de Teams

Teams les utilisateurs peuvent recevoir et répondre aux appels des standards automatiques cloud et des files d’attente d’appels directement à partir de leur client Teams.

## <a name="what-are-auto-attendants-and-call-queues"></a>Qu’est-ce que les standards automatiques et les files d’attente d’appels ?

Les standards automatiques cloud fournissent une série d’invites vocales ou un fichier audio que les appelants entendent au lieu d’un opérateur humain lorsqu’ils appellent une organisation. Un standard automatique permet aux utilisateurs de parcourir le système de menu, de passer des appels ou de rechercher des utilisateurs en utilisant un clavier téléphonique (DTMF) ou effectuer des entrées vocales à l'aide de la reconnaissance vocale.

Les files d’attente d’appels cloud incluent les messages d’accueil utilisés lorsqu’une personne appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher l’agent d’appel disponible suivant pour gérer l’appel pendant que les personnes qui appellent écoutent de la musique en attente. Vous pouvez créer des files d’attente d’appels uniques ou multiples pour votre organisation.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Gestion d’un standard automatique ou d’un appel de file d’attente d’appels

Les utilisateurs pourront différencier les appels entrants d’un standard automatique ou d’une file d’attente d’appels avant de répondre à l’appel. Avec le nom et/ou le numéro de l’appelant, chaque appel inclut des informations sur les personnes que l’appelant essayait d’atteindre, ce qui donne aux utilisateurs un meilleur contexte pour l’adressage de l’appelant.

L’illustration suivante montre comment un appel entrant à partir d’un standard automatique ou d’une file d’attente d’appels apparaîtra à un utilisateur.

![Capture d’écran d’une notification d’appel entrant.](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Une fois qu’un standard automatique ou un appel de file d’attente d’appels est répondu, l’utilisateur peut traiter l’appel comme n’importe quel autre appel &#x2014; il peut ajouter ou conférencer un autre utilisateur ou transférer l’appel à une autre partie. En outre, les appels de standard automatique sont transférés en fonction de la configuration de l’utilisateur.

> [!NOTE] 
> Les appels de file d’attente d’appels ne sont pas transférés en fonction de la configuration des règles de réponse aux appels de l’utilisateur. Cela permet de s’assurer que les appelants restent dans la file d’attente jusqu’à ce qu’un agent puisse répondre à l’appel et que l’appelant ne soit pas transféré de manière inattendue.

> Les agents ne sont pas avertis des appels manqués ou des messages vocaux pour les appels de file d’attente d’appels.

## <a name="supported-clients"></a>Clients pris en charge

La prise en charge des appels de standard automatique et de file d’attente d’appels est disponible dans les clients suivants :

-    client Microsoft Teams Windows (versions 32 et 64 bits)
-    Client Microsoft Teams pour Mac
-    Application Microsoft Teams pour iPhone
-    Application Microsoft Teams pour Android

Le client Teams est uniquement pris en charge avec un [mode de coexistence de Teams uniquement](/microsoftteams/setting-your-coexistence-and-upgrade-settings).

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurer la prise en charge du standard automatique et de la file d’attente d’appels pour Microsoft Teams

Pour recevoir des appels de standard automatique et de file d’attente d’appels sur Microsoft Teams, vous devez configurer votre stratégie d’interopérabilité et votre stratégie de mise à niveau. Passez en revue [la migration et l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md). Si vous n’avez pas configuré le standard automatique et/ou la file d’attente d’appels et souhaitez le faire, consultez [Configurer un standard automatique cloud](create-a-phone-system-auto-attendant.md) et [créer une file d’attente d’appels cloud](create-a-phone-system-call-queue.md).

## <a name="known-issues"></a>Problèmes connus

Lorsqu’un agent de file d’attente d’appels reçoit un appel sur son appareil mobile, l’appel peut être mis en attente si l’appareil est verrouillé. Les utilisateurs doivent d’abord déverrouiller l’appareil, puis répondre à l’appel.


## <a name="related-topics"></a>Voir aussi

[Créer une file d’attente d’appels cloud](create-a-phone-system-call-queue.md)

[Un standard Cloud automatique, qu’est-ce que c’est ?](what-are-phone-system-auto-attendants.md)

[Configurer un standard automatique dans le cloud](create-a-phone-system-auto-attendant.md)

