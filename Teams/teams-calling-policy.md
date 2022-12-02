---
title: 'Stratégies d’appel dans Microsoft Teams : fonctionnalités d’appel et de transfert d’appel'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Découvrez comment créer, modifier et ajouter des utilisateurs à des stratégies d’appel personnalisées dans Microsoft Teams, ainsi que différents paramètres de stratégie d’appel.
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
ms.openlocfilehash: a02df903574c7e7db796294ad90c9e05ab732eb0
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245747"
---
# <a name="calling-policies-calling-and-call-forwarding-features-in-teams"></a>Stratégies d’appel : fonctionnalités d’appel et de transfert d’appel dans Teams

Dans Microsoft Teams, les stratégies d’appel contrôlent les fonctionnalités d’appel et de transfert d’appel disponibles pour les utilisateurs. Les stratégies d’appel déterminent si un utilisateur peut passer des appels privés, utiliser le transfert d’appel ou la sonnerie simultanée à d’autres utilisateurs ou des numéros de téléphone externes, acheminer les appels vers la messagerie vocale, envoyer des appels à des groupes d’appels, utiliser la délégation pour les appels entrants et sortants, etc.

Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) créée automatiquement ou créer et attribuer des stratégies personnalisées.

## <a name="create-a-custom-calling-policy"></a>Créer une stratégie d’appel personnalisée

Suivez ces étapes pour créer une stratégie d’appel personnalisée.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à **Stratégies d’appel vocal** > .
2. Sélectionnez **Ajouter**.
3. Activez ou désactivez les fonctionnalités que vous souhaitez utiliser dans votre stratégie d’appel.
    - Par exemple, pour contrôler si les utilisateurs peuvent acheminer les appels entrants vers la messagerie vocale, sélectionnez **Activé** ou **Contrôlé par l’utilisateur**. Pour empêcher le routage vers la messagerie vocale, sélectionnez **Non activé**.
4. Sélectionnez **Enregistrer**.

## <a name="edit-a-calling-policy"></a>Modifier une stratégie d’appel

Suivez ces étapes pour modifier une stratégie d’appel existante.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Stratégies d’appel vocal** > .
2. Cliquez en regard de la stratégie à modifier, puis sélectionnez **Modifier**.
3. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Affecter une stratégie d’appel personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Paramètres de stratégie d’appel

Voici les paramètres que vous pouvez configurer pour les stratégies d’appel.

### <a name="make-private-calls"></a>Passer des appels privés

Ce paramètre contrôle toutes les fonctionnalités d’appel dans Teams. Désactivez cette option pour désactiver toutes les fonctionnalités d’appel dans Teams.

### <a name="cloud-recording-for-calling"></a>Enregistrement cloud pour l’appel

Ce paramètre contrôle si les utilisateurs peuvent enregistrer des appels. Cette option est désactivée par défaut.

### <a name="transcription"></a>Transcription

Ce paramètre contrôle si la transcription des appels est disponible pour vos utilisateurs. Cette option est désactivée par défaut.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Transfert d’appel et sonnerie simultanée aux personnes de votre organisation

Ce paramètre contrôle si les appels entrants peuvent être transférés à d’autres utilisateurs ou sonner une autre personne de votre organisation en même temps. Cette option est activée par défaut.

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Transfert d’appel et sonnerie simultanée vers des numéros de téléphone externes

Ce paramètre contrôle si les appels entrants peuvent être transférés à un numéro externe ou sonner un numéro externe en même temps. Cette option est activée par défaut.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>La messagerie vocale est disponible pour le routage des appels entrants

Ce paramètre permet d’envoyer des appels entrants à la messagerie vocale. Le paramètre par défaut est **Contrôlé par l’utilisateur**. Les options valides sont les suivantes :

- **Activé** La messagerie vocale est toujours disponible pour les appels entrants.
- **Non activé**  La messagerie vocale n’est pas disponible pour les appels entrants.
- **Contrôlé par l’utilisateur** Les utilisateurs peuvent déterminer s’ils souhaitent que la messagerie vocale soit disponible.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Les appels entrants peuvent être routés vers des groupes d’appels

Ce paramètre contrôle si les appels entrants peuvent être transférés à un groupe d’appels. Cette option est activée par défaut.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Délégation pour les appels entrants et sortants

Ce paramètre permet aux appels entrants d’être routés vers les délégués, ce qui permet aux délégués d’effectuer des appels sortants pour le compte des utilisateurs pour lesquels ils disposent d’autorisations déléguées. Ce paramètre est activé par défaut. Pour plus d’informations, consultez [Partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Empêcher la déviation des péages et envoyer des appels via le RTC

Si vous définissez cette option sur **Activé** , les appels sont envoyés via le réseau RTC et entraînent des frais au lieu de les envoyer via le réseau et de contourner les péages. Ce paramètre est désactivé par défaut.

### <a name="music-on-hold-for-pstn-calls"></a>Musique en attente pour les appels RTC

Ce paramètre vous permet d’activer ou de désactiver la musique en attente lorsqu’un appelant RTC est mis en attente. Il est activé par défaut. Ce paramètre ne s’applique pas aux fonctionnalités de parcage d’appel et de délégué de patron. En savoir plus sur la configuration de [la musique personnalisée](music-on-hold.md).

### <a name="busy-on-busy-when-in-a-call"></a>Occupé sur occupé lors d’un appel

Occupé lors d’un appel (également appelé « options occupées ») vous permet de configurer la façon dont les appels entrants sont gérés lorsqu’un utilisateur est déjà en appel ou en conférence ou qu’un appel est mis en attente. Les appels nouveaux ou entrants peuvent être rejetés avec un signal occupé ou peuvent être routés en conséquence selon les paramètres sans réponse de l’utilisateur. Quelle que soit la façon dont leurs options de disponibilité sont configurées, les utilisateurs d’un appel ou d’une conférence ou ceux qui ont un appel en attente ne sont pas empêchés de lancer de nouveaux appels ou conférences. Ce paramètre est défini sur **Non activé** par défaut.

- **Non activé** Aucune option occupée n’est activée et les appels nouveaux ou entrants peuvent toujours être passés à l’utilisateur lorsque l’utilisateur est déjà en appel.
- **Activé** Les appels nouveaux ou entrants sont rejetés avec un signal occupé.
- **En suspens** Les paramètres sans réponse de l’utilisateur seront utilisés, tels que le routage vers la messagerie vocale ou le transfert vers un autre utilisateur.

### <a name="web-pstn-calling"></a>Appel RTC web

Ce paramètre permet aux utilisateurs d’appeler des numéros RTC à l’aide du client web Teams. Cette option est activée par défaut.

### <a name="real-time-captions-in-teams-calls"></a>Sous-titres en temps réel dans les appels Teams

Ce paramètre contrôle si les sous-titres en temps réel dans les appels Teams sont disponibles pour vos utilisateurs. Cette option est activée par défaut.

### <a name="automatically-answer-incoming-meeting-invites"></a>Répondre automatiquement aux invitations aux réunions entrantes

Ce paramètre contrôle si les invitations aux réunions entrantes reçoivent automatiquement une réponse. Cette option est désactivée par défaut. Gardez à l’esprit que ce paramètre s’applique uniquement aux invitations aux réunions entrantes. Elle ne s’applique pas aux autres types d’appels.

### <a name="spam-filtering"></a>Filtrage du courrier indésirable

Ce paramètre vous permet de contrôler le type de filtrage du courrier indésirable disponible sur les appels entrants. Les vérifications De base et Captcha Interactive Voice (IVR) peuvent être effectuées. Cette option est activée par défaut.

### <a name="sip-devices-can-be-used-for-calls"></a>Les appareils SIP peuvent être utilisés pour les appels

Ce paramètre permet aux utilisateurs d’utiliser un appareil SIP pour passer et recevoir des appels. Cette option est désactivée par défaut.

### <a name="open-apps-in-browser-for-incoming-pstn-calls"></a>Ouvrir des applications dans le navigateur pour les appels RTC entrants

Ce paramètre contrôle si les applications sont automatiquement ouvertes dans le navigateur pour les appels RTC entrants à vos utilisateurs. Cela peut être utilisé pour passer le numéro de téléphone d’un appelant entrant à une application afin de rechercher l’enregistrement client associé pendant l’appel. Ce paramètre est désactivé par défaut.

Si cette option est activée, un lien vers l’application doit être fourni dans **l’URL pour ouvrir les applications dans le navigateur pour les appels RTC entrants** . Vous pouvez utiliser l’espace réservé {phone} pour passer le numéro de téléphone (au format E.164) à l’URL fournie. Vous pouvez également donner une URL générique sans espace réservé. Cela lance simplement l’URL répertoriée.

![Capture d’écran du paramètre de stratégie Ouvrir les applications dans le navigateur pour les appels RTC entrants.](media/teams-open-apps-in-browser-pstn.png)

## <a name="related-articles"></a>Articles connexes

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)

[Options de connectivité RTC](pstn-connectivity.md)

[Configurer les paramètres d’appel pour vos utilisateurs](user-call-settings.md)
