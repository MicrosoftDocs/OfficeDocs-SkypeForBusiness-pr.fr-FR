---
title: Stratégies de conservation dans Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Découvrez les paramètres de stratégie d’appel dans Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c35c2455c3164f04dd9fdbbb210e20809a719bc6
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835326"
---
<a name="calling-policies-in-microsoft-teams"></a>Stratégies de conservation dans Microsoft Teams
===================================

Dans Microsoft Teams, appel de contrôle des stratégies les appels et les fonctionnalités de transfert d’appel sont disponibles pour les utilisateurs. Les stratégies d’appel déterminent si un utilisateur peut effectuer des appels privées, utilisez le transfert d’appel ou acheminer les appels vers la messagerie vocale, envoyer les appels aux groupes d’appel, sonnerie simultanée à d’autres utilisateurs ou les numéros de téléphone externe, utilisent la délégation pour les appels entrants et sortants, et ainsi de suite. Une stratégie globale par défaut est créée automatiquement, mais les administrateurs peuvent également créer et affecter des stratégies appel personnalisés.

## <a name="create-a-custom-calling-policy"></a>Créer une stratégie personnalisée appelante

Suivez ces étapes pour créer une stratégie personnalisée appelante.

1. Dans le centre d’administration Microsoft Teams, sélectionnez **voix** > **stratégie de l’appel**.
2. Sélectionnez **nouvelle stratégie**.
3. Activer les fonctionnalités que vous souhaitez utiliser dans la stratégie de votre appel. Toutes les sélections sont **désactivées** par défaut.
4. Pour contrôler si les utilisateurs peuvent router les appels entrants vers la messagerie vocale, sélectionnez **toujours activé** ou **définis par les utilisateurs**. Pour empêcher le routage vers la messagerie vocale, sélectionnez **toujours désactivé**.
5. Cliquez sur **Enregistrer**.

## <a name="modify-an-existing-calling-policy"></a>Modifier un appel de stratégie existant

Suivez ces étapes pour modifier une stratégie de l’appel.

1. Dans le centre d’administration Microsoft Teams, sélectionnez **voix** > **stratégie de l’appel**.
2. Cliquez sur en regard de la stratégie que vous souhaitez modifier, puis sélectionnez **Modifier**.
3. Activer les fonctionnalités que vous souhaitez utiliser dans la stratégie de votre appel. Toutes les sélections sont **désactivées** par défaut.
4. Pour contrôler si les utilisateurs peuvent router les appels entrants vers la messagerie vocale, sélectionnez **toujours activé** ou **définis par les utilisateurs**. Pour empêcher le routage vers la messagerie vocale, sélectionnez **toujours désactivé**.
5. Cliquez sur **Enregistrer**.

## <a name="assign-a-calling-policy-to-a-user"></a>Affecter une stratégie appelante à un utilisateur

Suivez ces étapes pour attribuer une stratégie personnalisée appelante à un utilisateur.

1. Dans le centre d’administration Microsoft Teams, sélectionnez **voix** > **stratégie de l’appel**.
2. Cliquez sur en regard du nom de la stratégie pour le sélectionner, puis sélectionnez **Gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs** , recherchez le nom d’utilisateur. (Vous devez entrer au moins trois caractères).
4. Sélectionnez le nom d’utilisateur, puis sélectionnez **Ajouter**.
5. Cliquez sur **Enregistrer**.

## <a name="calling-policy-settings"></a>Paramètres de stratégie de l’appel

Utilisez les paramètres suivants pour créer une stratégie personnalisée appelante.

### <a name="user-can-make-private-calls"></a>Utilisateur peut passer des appels privées

Ce paramètre contrôle toutes les fonctionnalités d’appel dans les équipes. Désactivez cette option pour désactiver toutes les fonctionnalités d’appel dans les équipes.

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>Le transfert d’appel et la sonnerie simultanée à d’autres utilisateurs

Ce paramètre contrôle si les appels entrants peuvent être transférés à d’autres utilisateurs ou une autre personne peuvent faire sonner en même temps. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Le transfert d’appel et la sonnerie simultanée aux numéros de téléphone externe

Ce paramètre contrôle si les appels entrants peuvent être transférés vers un numéro externe ou un numéro externe peuvent faire sonner en même temps.

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>Messagerie vocale est disponible pour acheminer les appels entrants vers les utilisateurs

Ce paramètre active les appels entrants destinés à être envoyés vers la messagerie vocale. Les options valides sont les suivants :

   - **Toujours activé** Messagerie vocale est toujours disponible pour les appels entrants. 
   - **Toujours désactivé**  Messagerie vocale n’est pas disponible pour les appels entrants. 
   - **Utilisateur contrôlé**. Les utilisateurs peuvent déterminer s’ils veulent être disponible de la messagerie vocale.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Les appels entrants peuvent être acheminés pour appeler des groupes 

> [!Include [feature preview](includes/preview-feature.md)]

Ce paramètre contrôle si les appels entrants peuvent être transférés vers un groupe d’appel.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Autoriser la délégation pour les appels entrants et sortants

> [!Include [feature preview](includes/preview-feature.md)]

Ce paramètre active les appels entrants destinés à être acheminés vers les délégués, les délégués pour émettre des appels sortants part les utilisateurs pour lesquels ils ont délégué des autorisations. Pour plus d’informations, voir [partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Empêcher le contournement de média payant et envoyer les appels par le biais de la passerelle PSTN 

La valeur **sur** pour envoyer les appels via le réseau RTC et provoquer des frais au lieu de les envoyer via le réseau et en contournant le cas.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Occupé (e) sur occupé (e) est disponible pendant un appel

Occupé (e) sur occupé (e) (Options occupé (e))) est un nouveau paramètre dans les équipes stratégies appelant qui vous permet de configurer les appels entrants comment sont traités lorsqu’un utilisateur est déjà dans un appel ou une conférence ou a un appel mis en attente. Nouveaux appels entrants peuvent être rejetées avec un signal occupé (e). Vous pouvez activer les options de disponibilité au niveau du client ou au niveau de l’utilisateur. Quelle que soit la configuration des options de leurs disponibilitées, les utilisateurs dans un appel ou conférence ou par un appel en attente ne peuvent pas pas d’initier des nouveaux appels ou des conférences. Ce paramètre est désactivé par défaut.

## <a name="see-also"></a>Voir aussi

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)