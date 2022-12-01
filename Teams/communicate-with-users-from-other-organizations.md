---
title: Utiliser l’accès invité et l’accès externe pour collaborer avec des personnes extérieures à votre organisation
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
description: Découvrez comment appeler, converser, rechercher, puis ajouter des utilisateurs extérieurs à l’organisation dans Microsoft Teams à l’aide de l’accès externe et de l’accès invité.
ms.openlocfilehash: f416453a93c07945f9df55c863f76cbb8b736a78
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198316"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a>Utiliser l’accès invité et l’accès externe pour collaborer avec des personnes extérieures à votre organisation

Cet article décrit deux des options permettant de collaborer avec des contacts extérieurs à votre organisation :

- **Accès externe** : type de fédération qui permet aux utilisateurs de rechercher, d’appeler des personnes d’autres organisations, puis de discuter avec elles. Vous ne pouvez pas ajouter ces personnes à une équipe, sauf en tant qu’invitées.
- **Accès invité** : l’accès invité vous permet d’inviter des personnes extérieures à votre organisation à rejoindre une équipe. Les personnes invitées obtiennent un compte invité dans Azure Active Directory.

Pour obtenir une vue d’ensemble complète de la collaboration externe dans Microsoft 365, consultez [Vue d’ensemble des options de collaboration externe dans Microsoft 365](/microsoft-365/enterprise/external-guest-access).

## <a name="external-access-external-chat-and-meetings"></a>Accès externe (réunions et conversation externes)

Configurez l’accès externe si vous avez besoin de rechercher, d’appeler, de discuter, puis de configurer des réunions avec des personnes extérieures à votre organisation qui utilisent Teams, Skype Entreprise (en ligne ou en local) ou Skype. 

Par défaut, l'accès externe est activé pour tous les domaines. Vous pouvez restreindre l’accès externe en autorisant ou en bloquant des domaines spécifiques, ou en le désactivant.

![Capture d’écran des paramètres d’accès externe](media/external-access-federation-settings.png)

L’accès externe est disponible pour les locataires suivants :
- Comptes d’entreprise gérés
     - Entre commercial uniquement
     - Entre GCC uniquement
     - Entre GCC High uniquement
     - Entre DOD uniquement
- Comptes non gérés (personnels)
     - Entre les comptes Commerciaux et Personnels uniquement
- interopérabilité Skype Entreprise
     - Entre et entre commercial, GCC, GCC High et DoD
- Skype Interop
     - Entre Commercial et Skype uniquement

Si vous souhaitez configurer l’accès externe, veuillez consulter la rubrique [Gérer l'accès externe](manage-external-access.md). 

>[!NOTE]
> Les licences [Microsoft Teams gratuit (classique)](https://support.microsoft.com/office/welcome-to-microsoft-teams-free-classic-6d79a648-6913-4696-9237-ed13de64ae3c) ne prennent pas en charge l’accès externe.

## <a name="guest-access"></a>Accès invité

L’accès invité permet d’ajouter une personne extérieure à votre organisation à une équipe, dans laquelle elle peut discuter, appeler, rencontrer des participants, puis collaborer sur des fichiers. Les invités peuvent bénéficier de presque toutes les mêmes fonctionnalités Teams que les membres d’équipe natifs. Pour plus d’informations, voir [Expérience des invités dans Teams.](guest-experience.md)

Les invités sont ajoutés à Azure Active Directory de votre organisation en tant qu’utilisateurs B2B Collaboration et doivent se connecter à Teams à l’aide de leur compte invité. En d’autres termes, ils devront sans doute se déconnecter de leurs propres organisations pour se connecter à la vôtre.

L’accès invité est disponible pour les locataires suivants :

- Dans et entre Commercial et GCC
- Entre GCC High uniquement
- Entre DOD uniquement

Si vous souhaitez configurer l’accès invité pour Teams, veuillez consulter la rubrique [Collaborer avec des invités au sein d’une équipe](/microsoft-365/solutions/collaborate-as-team).

## <a name="compare-external-and-guest-access"></a>Comparer l’accès externe et l’accès invité

Les tableaux suivants montrent les différences entre l’utilisation de l’accès externe (fédération) et les invités. Dans les deux cas, vos utilisateurs identifient les personnes extérieures à votre organisation comme externes.

### <a name="things-your-users-can-do"></a>Actions réalisables par vos utilisateurs

| Vos utilisateurs peuvent | Utilisateurs de l’accès externe | Invités |
|---------|-----------------------|--------------------|
| Converser avec une personne d’une autre organisation | Oui | Oui |
| Appeler une personne d’une autre organisation | Oui | Oui |
| Voir si une personne d’une autre organisation est disponible pour un appel ou une conversation | Oui | Oui <sup>1</sup> |
| Rechercher des personnes d’autres organisations | Oui <sup>2</sup> | Non |
| Partager des fichiers | Non | Oui |
| Consulter le message d’absence du bureau d’une personne d’une autre organisation | Non | Oui |
| Bloquer une personne d’une autre organisation  | Non | Oui |
| Utiliser les @mentions | Oui<sup>3</sup> | Oui |

### <a name="things-people-outside-your-organization-can-do"></a>Actions réalisables par les personnes extérieures à votre organisation

| Les personnes extérieures à votre organisation peuvent | Utilisateurs de l’accès externe | Invités |
|---------|-----------------------|--------------------|
| Accéder aux ressources Teams | Non | Oui |
| Être ajoutées à une conversation de groupe | Oui | Oui |
| Être invitées à une réunion | Oui | Oui |
| Passer des appels privés | Oui | Oui<sup>5</sup> |
| Afficher le numéro de téléphone des participants à la réunion rendez-vous | Non<sup>4</sup> | Oui |
| Utiliser la vidéo sur IP | Oui | Oui<sup>5</sup> |
| Utiliser le partage d’écran | Oui<sup>3</sup> | Oui<sup>5</sup> |
| Utiliser la réunion instantanée | Non | Oui<sup>5</sup> |
| Modifier des messages envoyés | Oui<sup>3</sup> | Oui<sup>5</sup> |
| Supprimer des messages envoyés | Oui<sup>3</sup> | Oui<sup>5</sup> |
| Utiliser Giphy dans la conversation | Oui<sup>3</sup> | Oui<sup>5</sup> |
| Utiliser des mèmes dans la conversation | Oui<sup>3</sup> | Oui<sup>5</sup> |
| Utiliser des autocollants dans la conversation | Oui<sup>3</sup> | Oui<sup>5</sup> |
| La présence s’affiche. | Oui | Oui |
| Utiliser les @mentions | Oui<sup>3</sup> | Oui |

<br>

<sup>1</sup> À condition que l’utilisateur ait été ajouté en tant qu’invité et qu’il soit connecté avec le compte invité.<br>
<sup>2</sup> Uniquement par adresse e-mail ou SIP (Session Initiation Protocol).<br>
<sup>3</sup> Fonction prise en charge pour la conversation 1:1 entre utilisateurs Teams uniquement de deux organisations différentes. <br>
<sup>4</sup> By default, external participants can't see the phone numbers of dialed-in participants. If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams). To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md). <br>
<sup>5</sup> Fonction autorisée par défaut, mais l’administrateur Teams peut la désactiver

## <a name="related-topics"></a>Voir aussi

[Accès externe dans Teams](manage-external-access.md)

[Accès invité dans Teams](guest-access.md)
