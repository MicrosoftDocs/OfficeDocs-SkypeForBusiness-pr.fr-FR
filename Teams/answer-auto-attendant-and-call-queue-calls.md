---
title: Répondre aux appels dans la file d’attente ou du standard automatique directement à partir de Teams
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Décrit les standards automatiques du Cloud et les files d’attente d’appels, et explique comment vous pouvez répondre à ces appels dans Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e864e32409730373d98263215b0bcc35d9b404d
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825312"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Répondre aux appels dans la file d’attente ou du standard automatique directement à partir de Teams
===========================================================

Les utilisateurs teams peuvent recevoir des appels et y répondre à partir de standards automatiques Cloud et de files d’attente d’appels directement depuis leur client Teams. Pour les utilisateurs d’équipes, la fonction standard automatique est désormais disponible en général et la fonctionnalité de la file d’attente d’appels est disponible en aperçu. 

## <a name="what-are-auto-attendants-and-call-queues"></a>Présentation des standards automatiques et des files d’attente d’appels

Les standards automatiques du Cloud fournissent une série d’invites vocales ou un fichier audio que les appelants entendent à la place d’un opérateur humain au sein d’une organisation. Un standard automatique permet aux utilisateurs de parcourir le système de menu, de passer des appels ou de rechercher des utilisateurs en utilisant un clavier téléphonique (DTMF) ou effectuer des entrées vocales à l'aide de la reconnaissance vocale.

Les files d’attente d’appels Cloud incluent des messages d’accueil qui sont utilisés lorsque quelqu’un vous appelle pour appeler un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel alors que les personnes qui rejoignent les appels sont écouter de la musique pendant l’attente. Vous pouvez créer des files d’attente d’appels uniques ou multiples pour votre organisation.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Gestion d’un appel de standard automatique ou de file d’attente d’appels

Les utilisateurs peuvent différencier les appels entrants d’un standard automatique ou d’une file d’attente d’appels avant de répondre à l’appel. Outre le nom et/ou le numéro de l’appelant, chaque appel inclut des informations sur les personnes que l’appelant essayait de joindre, offrant ainsi aux utilisateurs un meilleur contexte pour l’adressage de l’appelant.

L’illustration suivante décrit le mode d’affichage d’un appel entrant d’un standard automatique ou d’une file d’attente d’appels.

![Capture d’écran d’une notification d’appel entrant](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Lorsque le standard automatique ou la file d’attente d’appels est reçu, l’utilisateur peut traiter l’appel comme tout autre appel &#x2014; il peut ajouter ou organiser une conférence à un autre utilisateur ou transférer l’appel vers une autre personne. De plus, les appels de standard automatique seront transférés en fonction de la configuration de l’utilisateur.

> [!NOTE] 
> Les appels de file d’attente d’appels ne sont pas transférés en fonction de la configuration de l’utilisateur. Cela permet de s’assurer que les appelants restent dans la file d’attente jusqu’à ce qu’un agent puisse répondre à l’appel et que l’appelant ne soit pas transféré de manière inattendue.

## <a name="supported-clients"></a>Clients pris en charge

La prise en charge des appels de standard automatique et de file d’attente d’appels est disponible dans les clients suivants :

-   Client Microsoft Teams (versions 32 et 64 bits)
-   Client Microsoft teams Mac
-   Application Microsoft teams pour iPhone
-   Application Android Microsoft teams

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurer le standard automatique et la prise en charge de la file d’attente des appels pour Microsoft teams

Pour recevoir des appels de standard automatique et de file d’attente d’appels sur Microsoft Teams, vous devez configurer votre stratégie d’interopérabilité et votre stratégie de mise à niveau. Passez en revue la [migration et l’interopérabilité des organisations qui utilisent des équipes dans Skype entreprise](migration-interop-guidance-for-teams-with-skype.md). Si vous n’avez pas configuré le standard automatique et/ou la file d’attente d’appels, puis souhaitez le faire, voir [configurer un standard automatique Cloud](create-a-phone-system-auto-attendant.md) et [créer une file d’attente d’appels Cloud](create-a-phone-system-call-queue.md).

## <a name="related-topics"></a>Rubriques connexes

-   [Qu’est-ce que le système téléphonique dans Office 365](what-is-phone-system-in-office-365.md)
-   [Créer une file d’attente d’appels cloud](create-a-phone-system-call-queue.md)
-   [Un standard Cloud automatique, qu’est-ce que c’est ?](what-are-phone-system-auto-attendants.md)
-   [Configurer un standard automatique dans le cloud](create-a-phone-system-auto-attendant.md)

