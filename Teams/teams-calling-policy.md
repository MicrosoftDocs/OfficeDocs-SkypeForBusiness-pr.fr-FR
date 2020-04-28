---
title: Stratégies de conservation dans Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
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
ms.openlocfilehash: a94bf072aa4db0ba0b3f65fb5340c22ab09581e4
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43914013"
---
<a name="calling-policies-in-microsoft-teams"></a>Stratégies de conservation dans Microsoft Teams
===================================

Dans Microsoft Teams, les stratégies d’appel contrôlent les fonctionnalités d’appel et de transfert d’appel disponibles pour les utilisateurs. Les politiques d’appel déterminent si un utilisateur peut passer des appels privés, utiliser le transfert d’appel ou la sonnerie simultanée d’autres utilisateurs ou des numéros de téléphone externes, diriger les appels vers la boîte vocale, envoyer les appels vers les groupes d’appels, utiliser la délégation pour les appels entrants et sortants, et ainsi de suite. Une stratégie globale par défaut est créée automatiquement, mais les administrateurs peuvent également créer et attribuer des stratégies d’appel personnalisées.

## <a name="create-a-custom-calling-policy"></a>Créer une stratégie d’appel personnalisée

Suivez ces étapes pour créer une stratégie d’appel personnalisée.

1. Dans le centre d’administration de Microsoft Teams, sélectionnez**politique d’appel** **vocal** > .
2. Sélectionnez **nouvelle stratégie**.
3. Activez les fonctionnalités que vous voulez utiliser dans votre stratégie d’appel. Toutes les sélections sont **Désdésactivées** par défaut.
4. Pour contrôler si les utilisateurs peuvent diriger les appels entrants vers la boîte vocale, sélectionnez **toujours activé** ou contrôlé par l' **utilisateur**. Pour empêcher le routage vers la boîte vocale, sélectionnez **toujours désactivé**.
5. Sélectionnez **Save (enregistrer**).

## <a name="modify-an-existing-calling-policy"></a>Modifier une stratégie d’appel existante

Pour modifier une stratégie d’appel existante, procédez comme suit.

1. Dans le centre d’administration de Microsoft Teams, sélectionnez**politique d’appel** **vocal** > .
2. Cliquez sur en regard de la stratégie que vous voulez modifier, puis sélectionnez **modifier**.
3. Activez les fonctionnalités que vous voulez utiliser dans votre stratégie d’appel. Toutes les sélections sont **Désdésactivées** par défaut.
4. Pour contrôler si les utilisateurs peuvent diriger les appels entrants vers la boîte vocale, sélectionnez **toujours activé** ou contrôlé par l' **utilisateur**. Pour empêcher le routage vers la boîte vocale, sélectionnez **toujours désactivé**.
5. Sélectionnez **Save (enregistrer**).

## <a name="assign-a-calling-policy-to-a-user"></a>Assigner une stratégie d’appel à un utilisateur

Pour attribuer une stratégie d’appel personnalisée à un utilisateur, procédez comme suit.

1. Dans le centre d’administration de Microsoft Teams, sélectionnez**politique d’appel** **vocal** > .
2. Cliquez sur en regard du nom de la stratégie pour la sélectionner, puis sélectionnez **gérer les utilisateurs**.
3. Dans le volet **gérer les utilisateurs** , recherchez le nom de l’utilisateur. (Vous devez entrer au moins trois caractères.)
4. Sélectionnez le nom de l’utilisateur, puis sélectionnez **Ajouter**.
5. Sélectionnez **Save (enregistrer**).

## <a name="calling-policy-settings"></a>Paramètres de la stratégie d’appel

Utilisez les paramètres suivants pour créer une stratégie d’appel personnalisée.

### <a name="user-can-make-private-calls"></a>L’utilisateur peut passer des appels privés

Ce paramètre contrôle toutes les fonctions d’appel dans Teams. Désactivez cette fonctionnalité pour désactiver toutes les fonctionnalités d’appel dans Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>Transfert d’appel et sonnerie simultanée à d’autres utilisateurs

Ce paramètre détermine si les appels entrants peuvent être transférés à d’autres utilisateurs ou pour appeler une autre personne en même temps. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Transfert d’appel et sonnerie simultanée sur les numéros de téléphone externes

Ce paramètre détermine si les appels entrants peuvent être transférés vers un numéro externe ou pour appeler un numéro externe en même temps.

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>Le message vocal est disponible pour le routage des appels entrants vers les utilisateurs.

Ce paramètre permet d’envoyer les appels entrants vers la boîte vocale. Les options valides sont les suivantes :

   - **Toujours activé** La boîte vocale est toujours disponible pour les appels entrants. 
   - **Toujours désactivé**  La boîte vocale n’est pas disponible pour les appels entrants. 
   - **Contrôle utilisateur**. Les utilisateurs peuvent déterminer s’ils veulent disposer de la boîte vocale.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Les appels entrants peuvent être routés vers des groupes d’appels 

> [!Include [feature preview](includes/preview-feature.md)]

Ce paramètre détermine si les appels entrants peuvent être transférés vers un groupe d’appels.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Autoriser la délégation pour les appels entrants et sortants

> [!Include [feature preview](includes/preview-feature.md)]

Ce paramètre permet à des délégués entrants d’être routés aux délégués, permettant ainsi aux délégués de passer des appels sortants au nom des utilisateurs pour lesquels ils disposent d’autorisations déléguées. Pour plus d’informations, consultez [la rubrique partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Empêcher le contournement payant et envoyer les appels via PSTN 

Le fait de définir ce paramètre sur **activé** permet d’envoyer des appels par le biais du réseau PSTN et d’engendrer des frais au lieu de les envoyer par le biais du réseau et de sauter les numéros.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Le niveau occupé est disponible pendant un appel

Occupé sur occupé (options occupées)) est un nouveau paramètre dans le cadre de la stratégie d’appel d’équipes qui vous permet de configurer le mode de gestion des appels entrants lorsqu’un utilisateur se trouve déjà dans un appel ou une conférence ou qu’un appel est en attente. Les appels nouveaux ou reçus peuvent être rejetés avec un signal occupé. Vous pouvez activer les options occupées au niveau du client ou au niveau de l’utilisateur. Quelle que soit la façon dont leurs options occupées sont configurées, les utilisateurs d’un appel ou d’une conférence ou ceux qui disposent d’un appel en attente ne peuvent pas lancer de nouveaux appels ou conférences. Ce paramètre est désactivé par défaut.

### <a name="allow-music-on-hold"></a>Autoriser la musique en attente

Ce paramètre vous permet d’activer ou de désactiver la musique lors de la mise en attente d’un appelant PSTN. Elle est activée par défaut. Ce paramètre ne s’applique pas aux fonctionnalités de délégué de parc et de dédirection, et est uniquement disponible via PowerShell actuellement. 

## <a name="see-also"></a>Voir aussi

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
