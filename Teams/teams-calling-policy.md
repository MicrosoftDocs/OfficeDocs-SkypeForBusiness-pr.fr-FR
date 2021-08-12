---
title: 'Stratégies d’appel Microsoft Teams : fonctionnalités d’appel et de forwarding d’appel'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Découvrez comment créer, modifier et ajouter des utilisateurs à des stratégies d’appel personnalisées dans Microsoft Teams, ainsi que différents paramètres de stratégie d’appel.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e38a566e025c711a9b17a050137e67af7507e63d5c5e829ba4448ee4a1577790
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309243"
---
#  <a name="calling-and-call-forwarding-in-teams"></a>Appel et forwarding d’appel dans Teams

Dans Microsoft Teams, les stratégies d’appel contrôlent les fonctionnalités d’appel et de transfert d’appel disponibles pour les utilisateurs. Les stratégies d’appel déterminent si un utilisateur peut passer des appels privés, utiliser le forwarding d’appel ou la sonnerie simultanée vers d’autres utilisateurs ou des numéros de téléphone externes, router les appels vers la messagerie vocale, envoyer des appels à des groupes d’appels, utiliser la délégation pour les appels entrants et sortants, etc.

Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) créée automatiquement ou créer et affecter des stratégies personnalisées.

## <a name="create-a-custom-calling-policy"></a>Créer une stratégie d’appel personnalisée

Suivez ces étapes pour créer une stratégie d’appel personnalisée.

1. Dans le navigation gauche du centre d’administration Microsoft Teams, allez aux **stratégies**  >  **d’appel vocal.**
2. Sélectionnez **Ajouter**.
3. Activez ou désactivez les fonctionnalités que vous souhaitez utiliser dans votre stratégie d’appel.
4. Pour contrôler si les utilisateurs peuvent acheminer les appels entrants vers la messagerie vocale, sélectionnez **Activé** ou **Contrôlé par l’utilisateur**. Pour empêcher le routage vers la messagerie vocale, sélectionnez **Désactivé**.
5. Sélectionnez **Enregistrer**.

## <a name="edit-a-calling-policy"></a>Modifier une stratégie d’appel

Suivez ces étapes pour modifier une stratégie d’appel existante.

1. Dans le navigation gauche du centre d’administration Microsoft Teams, sélectionnez **stratégies**  >  **d’appel vocal.**
2. Cliquez en côté de la stratégie à modifier, puis sélectionnez **Modifier.**
3. A apporté les modifications que vous souhaitez, puis cliquez sur **Enregistrer.**

## <a name="assign-a-custom-calling-policy-to-users"></a>Affecter une stratégie d’appel personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Paramètres de stratégie d’appel

Voici les paramètres que vous pouvez configurer pour les stratégies d’appel.

### <a name="make-private-calls"></a>Passer des appels privés

Ce paramètre contrôle toutes les fonctionnalités d’appel Teams. Désactivez cette option pour désactiver toutes les fonctionnalités d’appel dans Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Transfert d'appel et sonnerie simultanée de membres de votre organisation

Ce paramètre contrôle si les appels entrants peuvent être transmis à d’autres utilisateurs ou peuvent sonner en même temps. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Transfert d'appel et sonnerie simultanée vers des numéros de téléphone externes

Ce paramètre contrôle si les appels entrants peuvent être transmis à un numéro externe ou sonner un numéro externe en même temps.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>La messagerie vocale est disponible pour le routage des appels entrants

Ce paramètre permet d’envoyer des appels entrants à la messagerie vocale. Les options valides sont les :

- **Activé** La messagerie vocale est toujours disponible pour les appels entrants.
- **Désactivé**  La messagerie vocale n’est pas disponible pour les appels entrants.
- **Utilisateur contrôlé** Les utilisateurs peuvent déterminer s’ils souhaitent que la messagerie vocale soit disponible.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Les appels entrants peuvent être acheminés vers des groupes d'appels

Ce paramètre contrôle si les appels entrants peuvent être transmis à un groupe d’appels.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Délégation pour les appels entrants et sortants

Ce paramètre permet de router les appels entrants vers des délégués, ce qui permet aux délégués d’effectuer des appels sortants pour le compte des utilisateurs pour lesquels ils ont des autorisations déléguées. Pour plus d’informations, [voir Partager une ligne téléphonique avec un délégué.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Empêchez le contournement de numéro payant et acheminer les appels via le RTC 

Le fait de définir ce paramètre sur **On** envoie des appels via le réseau téléphonique téléphonique public (PSTN) et initie des frais plutôt que de les envoyer via le réseau et de contourner les frais de frais.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>Busy on busy is available when in a call

Busy on Busy (Busy Options) vous permet de configurer la façon dont les appels entrants sont gérés lorsqu’un utilisateur est déjà en cours d’appel ou de conférence ou qu’un appel est mis en attente. Les appels nouveaux ou entrants peuvent être rejetés avec une signal occupé ou acheminés en conséquence aux paramètres sans réponse de l’utilisateur. Vous pouvez activer les options occupé(s) au niveau du client ou de l’utilisateur. Quelle que soit la façon dont les options de occupé(s) sont configurées, les utilisateurs d’un appel ou d’une conférence ou ceux qui ont un appel en attente ne sont pas empêchés de lancer de nouveaux appels ou conférences. Ce paramètre est désactivé par défaut.

### <a name="web-pstn-calling"></a>Appel PSTN web

Ce paramètre permet aux utilisateurs d’appeler des numéros PSTN à l’aide Teams client web.

### <a name="incoming-meeting-invites-are-automatically-answered"></a>Les invitations aux réunions entrantes sont automatiquement répondues

Ce paramètre contrôle si les invitations aux réunions entrantes sont automatiquement répondues. Il est désactivé par défaut. N’oubliez pas que ce paramètre s’applique uniquement aux invitations aux réunions entrantes. Elle ne s’applique pas aux autres types d’appels.

### <a name="allow-music-on-hold"></a>Autoriser la musique en attente

Ce paramètre vous permet d’activer ou de désactiver l’attente musicale lorsqu’un appelant PSTN est mis en attente. Il est activé par défaut. Ce paramètre ne s’applique pas aux fonctionnalités de parcage d’appel et de délégué de responsable et n’est actuellement disponible que via PowerShell.

## <a name="related-articles"></a>Articles connexes

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)
