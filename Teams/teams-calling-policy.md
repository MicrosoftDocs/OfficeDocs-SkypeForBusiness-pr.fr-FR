---
title: 'Stratégies d’appel dans Microsoft Teams : fonctionnalités d’appel et de transfert d’appel'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Découvrez comment créer, modifier et ajouter des utilisateurs à des stratégies d’appel personnalisées dans Microsoft Teams, ainsi qu’à différents paramètres de stratégie d’appel.
ms.localizationpriority: medium
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
ms.openlocfilehash: 5097586825b231decd220a30bdde85bf258e27fc
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2022
ms.locfileid: "65313106"
---
# <a name="calling-and-call-forwarding-in-teams"></a>Appel et transfert d’appel dans Teams

Dans Microsoft Teams, les stratégies d’appel contrôlent les fonctionnalités d’appel et de transfert d’appel disponibles pour les utilisateurs. Les stratégies d’appel déterminent si un utilisateur peut effectuer des appels privés, utiliser le transfert d’appel ou sonner simultanément vers d’autres utilisateurs ou numéros de téléphone externes, acheminer les appels vers la messagerie vocale, envoyer des appels à des groupes d’appels, utiliser la délégation pour les appels entrants et sortants, et ainsi de suite.

Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) qui est créée automatiquement ou créer et affecter des stratégies personnalisées.

## <a name="create-a-custom-calling-policy"></a>Créer une stratégie d’appel personnalisée

Suivez ces étapes pour créer une stratégie d’appel personnalisée.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **stratégies VoiceCalling** > .
2. Sélectionnez **Ajouter**.
3. Activez ou désactivez les fonctionnalités que vous souhaitez utiliser dans votre stratégie d’appel.
4. Pour contrôler si les utilisateurs peuvent acheminer les appels entrants vers la messagerie vocale, **sélectionnez Activé** ou **Contrôlé par l’utilisateur**. Pour empêcher le routage vers la messagerie vocale, sélectionnez **Désactivé**.
5. Sélectionnez **Enregistrer**.

## <a name="edit-a-calling-policy"></a>Modifier une stratégie d’appel

Suivez ces étapes pour modifier une stratégie d’appel existante.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, sélectionnez **Stratégies** **VoiceCalling** > .
2. Cliquez en regard de la stratégie à modifier, puis **sélectionnez Modifier**.
3. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Affecter une stratégie d’appel personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Appel des paramètres de stratégie

Voici les paramètres que vous pouvez configurer pour les stratégies d’appel.

### <a name="make-private-calls"></a>Passer des appels privés

Ce paramètre contrôle toutes les fonctionnalités d’appel dans Teams. Désactivez cette option pour désactiver toutes les fonctionnalités d’appel dans Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Transfert d’appel et sonnerie simultanée aux membres de votre organisation

Ce paramètre détermine si les appels entrants peuvent être transférés à d’autres utilisateurs ou si une autre personne peut sonner en même temps.

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Transfert d’appel et sonnerie simultanée vers des numéros de téléphone externes

Ce paramètre détermine si les appels entrants peuvent être transférés vers un numéro externe ou sonner un numéro externe en même temps.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>La messagerie vocale est disponible pour le routage des appels entrants

Ce paramètre permet d’envoyer des appels entrants à la messagerie vocale. Les options valides sont les suivantes :

- **Activé** La messagerie vocale est toujours disponible pour les appels entrants.
- **Handicapés**  La messagerie vocale n’est pas disponible pour les appels entrants.
- **Contrôlé par l’utilisateur** Les utilisateurs peuvent déterminer s’ils souhaitent que la messagerie vocale soit disponible.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Les appels entrants peuvent être routées vers des groupes d’appels

Ce paramètre contrôle si les appels entrants peuvent être transférés à un groupe d’appels.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Délégation pour les appels entrants et sortants

Ce paramètre permet de router les appels entrants vers les délégués, ce qui permet aux délégués d’effectuer des appels sortants au nom des utilisateurs pour lesquels ils disposent d’autorisations déléguées. Pour plus d’informations, consultez [Partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Empêcher le contournement des péages et envoyer des appels via le RTC

Si vous définissez ce paramètre **sur Activé** , les appels sont envoyés via le rtc et entraînent des frais au lieu de les envoyer via le réseau et de contourner les péages.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>Busy on busy est disponible lors d’un appel

Busy on Busy (Busy Options) vous permet de configurer la façon dont les appels entrants sont gérés lorsqu’un utilisateur est déjà dans un appel ou une conférence ou qu’un appel est mis en attente. Les appels nouveaux ou entrants peuvent être rejetés avec un signal occupé ou être acheminés en conséquence vers les paramètres sans réponse de l’utilisateur. Vous pouvez activer les options de disponibilité au niveau du locataire ou de l’utilisateur. Quelle que soit la configuration de leurs options de disponibilité, les utilisateurs d’une téléconférence ou d’un appel en attente ne sont pas empêchés de lancer de nouveaux appels ou conférences. Ce paramètre est désactivé par défaut.

### <a name="web-pstn-calling"></a>Appel RTC web

Ce paramètre permet aux utilisateurs d’appeler des numéros RTC à l’aide du client web Teams.

### <a name="incoming-meeting-invites-are-automatically-answered"></a>Les invitations aux réunions entrantes sont automatiquement répondues

Ce paramètre détermine si les invitations aux réunions entrantes sont automatiquement répondues. Cette option est désactivée par défaut. N’oubliez pas que ce paramètre s’applique uniquement aux invitations à des réunions entrantes. Il ne s’applique pas à d’autres types d’appels.

### <a name="allow-music-on-hold"></a>Autoriser la musique en attente

Ce paramètre vous permet d’activer ou de désactiver la musique en attente lorsqu’un appelant RTC est mis en attente. Il est activé par défaut. Ce paramètre ne s’applique pas aux fonctionnalités de parcage d’appel et de délégué de boss.

### <a name="allow-sip-devices-calling"></a>Autoriser l’appel d’appareils SIP

Ce paramètre permet aux utilisateurs d’utiliser un appareil SIP pour passer et recevoir des appels.

### <a name="spam-filtering"></a>Filtrage du courrier indésirable

Ce paramètre vous permet de contrôler le type de filtrage du courrier indésirable disponible sur les appels entrants.

### <a name="call-recording-live-captions-and-transcription"></a>Enregistrement des appels, légendes en direct et transcription

Ces paramètres vous permettent de contrôler si l’enregistrement des appels, les légendes en direct et la transcription sont disponibles pour les utilisateurs.

## <a name="related-articles"></a>Articles connexes

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy)

[Remove-CsTeamsCallingPolicy](/powershell/module/skype/remove-csteamscallingpolicy)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)
