---
title: Stratégies de conservation dans Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Découvrez comment créer, modifier et ajouter des utilisateurs à des stratégies d’appel personnalisées dans Microsoft Teams, ainsi que divers paramètres de stratégie d’appel.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 030be626574e7acd3aa2116595acaba757eaa5af
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44942041"
---
<a name="calling-policies-in-microsoft-teams"></a>Stratégies de conservation dans Microsoft Teams
===================================

Dans Microsoft Teams, les stratégies d’appel contrôlent les fonctionnalités d’appel et de transfert d’appel disponibles pour les utilisateurs. Les politiques d’appel déterminent si un utilisateur peut passer des appels privés, utiliser le transfert d’appel ou la sonnerie simultanée d’autres utilisateurs ou des numéros de téléphone externes, diriger les appels vers la boîte vocale, envoyer les appels vers les groupes d’appels, utiliser la délégation pour les appels entrants et sortants, et ainsi de suite.

Vous pouvez utiliser la stratégie globale par défaut de l’organisation créée automatiquement, ou créer et affecter des stratégies personnalisées.

## <a name="create-a-custom-calling-policy"></a>Créer une stratégie d’appel personnalisée

Suivez ces étapes pour créer une stratégie d’appel personnalisée.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies d’appel**vocal.
2. Cliquez sur **Ajouter**.
3. Activez ou désactivez les fonctionnalités que vous voulez utiliser dans votre stratégie d’appel.
4. Pour contrôler si les utilisateurs peuvent diriger les appels entrants vers la boîte vocale, sélectionnez **activé** ou contrôlé par l' **utilisateur**. Pour empêcher le routage vers la boîte vocale, sélectionnez **désactivé**.
5. Sélectionnez **Save (enregistrer**).

## <a name="edit-a-calling-policy"></a>Modifier une stratégie d’appel

Pour modifier une stratégie d’appel existante, procédez comme suit.

1. Dans le volet de navigation de gauche du centre d’administration de **Voice**Microsoft Teams, sélectionnez  >  **politiques d’appel**vocal.
2. Cliquez sur en regard de la stratégie que vous voulez modifier, puis sélectionnez **modifier**.
3. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Assigner une stratégie d’appel personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Paramètres de la stratégie d’appel

Voici les paramètres que vous pouvez configurer pour les stratégies d’appel.

### <a name="make-private-calls"></a>Passer des appels privés

Ce paramètre contrôle toutes les fonctions d’appel dans Teams. Désactivez cette fonctionnalité pour désactiver toutes les fonctionnalités d’appel dans Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Transfert d’appel et sonnerie simultanée pour les membres de votre organisation

Ce paramètre détermine si les appels entrants peuvent être transférés à d’autres utilisateurs ou pour appeler une autre personne en même temps. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Transfert d’appel et sonnerie simultanée sur les numéros de téléphone externes

Ce paramètre détermine si les appels entrants peuvent être transférés vers un numéro externe ou pour appeler un numéro externe en même temps.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>La boîte vocale est disponible pour le routage des appels entrants

Ce paramètre permet d’envoyer les appels entrants vers la boîte vocale. Les options valides sont les suivantes :

- **Activée** La boîte vocale est toujours disponible pour les appels entrants.
- **Désactivé**  La boîte vocale n’est pas disponible pour les appels entrants.
- **Contrôle utilisateur** Les utilisateurs peuvent déterminer s’ils veulent disposer de la boîte vocale.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Les appels entrants peuvent être routés vers des groupes d’appels 

> [!Include [feature preview](includes/preview-feature.md)]

Ce paramètre détermine si les appels entrants peuvent être transférés vers un groupe d’appels.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Autoriser la délégation pour les appels entrants et sortants

> [!Include [feature preview](includes/preview-feature.md)]

Ce paramètre permet à des délégués entrants d’être routés aux délégués, permettant ainsi aux délégués de passer des appels sortants au nom des utilisateurs pour lesquels ils disposent d’autorisations déléguées. Pour plus d’informations, consultez [la rubrique partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Empêcher le contournement payant et envoyer les appels via PSTN 

Le fait de définir ce paramètre sur **activé** permet d’envoyer des appels par le biais du réseau PSTN et d’engendrer des frais au lieu de les envoyer par le biais du réseau et de sauter les numéros.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Le niveau occupé est disponible pendant un appel

Occupé dans occupé (les options occupées) est un nouveau paramètre qui vous permet de configurer le mode de gestion des appels entrants lorsqu’un utilisateur se trouve déjà en communication ou qu’un appel est en attente. Les appels nouveaux ou reçus peuvent être rejetés avec un signal occupé. Vous pouvez activer les options occupées au niveau du client ou au niveau de l’utilisateur. Quelle que soit la façon dont leurs options occupées sont configurées, les utilisateurs d’un appel ou d’une conférence ou ceux qui disposent d’un appel en attente ne peuvent pas lancer de nouveaux appels ou conférences. Ce paramètre est désactivé par défaut.

### <a name="allow-web-pstn-calling"></a>Autoriser les appels RTC Web

Ce paramètre permet aux utilisateurs d’appeler des numéros PSTN à l’aide du client Web Teams.

### <a name="allow-music-on-hold"></a>Autoriser la musique en attente

Ce paramètre vous permet d’activer ou de désactiver la musique lors de la mise en attente d’un appelant PSTN. Elle est activée par défaut. Ce paramètre ne s’applique pas aux fonctionnalités de délégué de parc et de dédirection, et n’est actuellement disponible que via PowerShell.

## <a name="related-topics"></a>Sujets associés

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)
