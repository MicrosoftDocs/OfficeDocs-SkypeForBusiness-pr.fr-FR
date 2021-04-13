---
title: Stratégies de conservation dans Microsoft Teams
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
ms.openlocfilehash: e469cc183134bab35855e83257126029ce78a8cc
ms.sourcegitcommit: c80af314f1a573f99dd66858301c004ccc5410d6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51653941"
---
<a name="calling-policies-in-microsoft-teams"></a>Stratégies de conservation dans Microsoft Teams
===================================

Dans Microsoft Teams, les stratégies d’appel contrôlent les fonctionnalités d’appel et de forwardage disponibles pour les utilisateurs. Les stratégies d’appel déterminent si un utilisateur peut passer des appels privés, utiliser le forwarding d’appel ou une sonnerie simultanée vers d’autres utilisateurs ou des numéros de téléphone externes, router les appels vers la messagerie vocale, envoyer des appels à des groupes d’appels, utiliser la délégation pour les appels entrants et sortants, etc.

Vous pouvez utiliser la stratégie globale (à l’échelle de l’organisation par défaut) créée automatiquement, ou créer et attribuer des stratégies personnalisées.

## <a name="create-a-custom-calling-policy"></a>Créer une stratégie d’appel personnalisée

Pour créer une stratégie d’appel personnalisée, suivez ces étapes.

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à **Stratégies**  >  **d’appel vocal.**
2. Sélectionnez **Ajouter**.
3. Activer ou désactiver les fonctionnalités que vous souhaitez utiliser dans votre stratégie d’appel.
4. Pour contrôler si les utilisateurs peuvent router les appels entrants vers la messagerie vocale, sélectionnez **Activé** ou **Utilisateur contrôlé.** Pour empêcher le routage vers la messagerie vocale, **sélectionnez Désactivé.**
5. Sélectionnez **Enregistrer**.

## <a name="edit-a-calling-policy"></a>Modifier une stratégie d’appel

Pour modifier une stratégie d’appel existante, suivez ces étapes.

1. Dans le navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Stratégies**  >  **d’appel vocal.**
2. Cliquez en côté de la stratégie à modifier, puis sélectionnez **Modifier.**
3. A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**

## <a name="assign-a-custom-calling-policy-to-users"></a>Affecter une stratégie d’appel personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Paramètres de stratégie d’appel

Voici les paramètres que vous pouvez configurer pour les stratégies d’appel.

### <a name="make-private-calls"></a>Passer des appels privés

Ce paramètre contrôle toutes les fonctionnalités d’appel dans Teams. Désactiver cette fonctionnalité pour désactiver toutes les fonctionnalités d’appel dans Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Call forwarding and simultaneous ringing to people in your organization

Ce paramètre contrôle si les appels entrants peuvent être transmis à d’autres utilisateurs ou faire sonner une autre personne en même temps. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Call forwarding and simultaneous ringing to external phone numbers

Ce paramètre contrôle si les appels entrants peuvent être transmis à un numéro externe ou faire sonner un numéro externe en même temps.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>La messagerie vocale est disponible pour les appels entrants de routage

Ce paramètre permet d’envoyer des appels entrants vers la messagerie vocale. Les options valides sont les :

- **Activé** La messagerie vocale est toujours disponible pour les appels entrants.
- **Désactivé**  La messagerie vocale n’est pas disponible pour les appels entrants.
- **Utilisateur contrôlé** Les utilisateurs peuvent déterminer s’ils souhaitent que la messagerie vocale soit disponible.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Les appels entrants peuvent être acheminés vers des groupes d’appels 

Ce paramètre contrôle si les appels entrants peuvent être transmis à un groupe d’appels.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Autoriser la délégation pour les appels entrants et sortants

Ce paramètre permet de router les appels entrants vers des délégués, ce qui permet aux délégués de réaliser des appels sortants pour le compte des utilisateurs pour lesquels ils ont des autorisations de délégué. Pour plus d’informations, [voir Partager une ligne téléphonique avec un délégué.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Empêcher la dérivation et l’envoi d’appels via le PSTN 

La définition de ce paramètre sur **Ôter** envoie des appels via le réseau PSTN et incurver des frais au lieu de les envoyer via le réseau sans passer par les frais de téléphone gratuits.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Occupé(elle) est disponible pendant un appel

Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold. Les appels entrants ou nouveaux peuvent être rejetés avec un signal occupé ou acheminés en conséquence vers les paramètres sans réponse de l’utilisateur. Vous pouvez activer les options de occupé(ive) au niveau du client ou de l’utilisateur. Quelle que soit la configuration de leurs options de occupé, les utilisateurs d’un appel ou d’une conférence ou ceux avec un appel en attente ne sont pas empêchés de lancer de nouveaux appels ou conférences. Ce paramètre est désactivé par défaut.

### <a name="allow-web-pstn-calling"></a>Autoriser les appels PSTN Web

Ce paramètre permet aux utilisateurs d’appeler des numéros PSTN à l’aide du client web Teams.

### <a name="allow-music-on-hold"></a>Autoriser l’attente musicale

Ce paramètre vous permet d’activer ou de désactiver l’attente musicale lorsqu’un appelant PSTN est mis en attente. Elle est désactivée par défaut. Ce paramètre ne s’applique pas aux fonctionnalités de parcage d’appel et de délégué de responsable et est actuellement disponible uniquement via PowerShell.

## <a name="related-topics"></a>Voir aussi

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)