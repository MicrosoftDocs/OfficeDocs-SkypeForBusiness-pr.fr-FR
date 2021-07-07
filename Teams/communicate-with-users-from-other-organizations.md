---
title: Utiliser l’accès invité et l’accès externe pour collaborer avec des personnes extérieures à votre organisation
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Priority
description: Découvrez comment appeler, discuter, rechercher, puis ajouter des utilisateurs extérieures à l’organisation dans Microsoft Teams à l’aide de l’accès externe (fédération) et de l’accès invité.
ms.openlocfilehash: bda5652aedd8d071984334a3851e50ba52400943
ms.sourcegitcommit: 89e26d9ffca180e56233984bf0a341b3c3ec7208
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "53301999"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a>Utiliser l’accès invité et l’accès externe pour collaborer avec des personnes extérieures à votre organisation

Lorsque vous avez besoin de communiquer, puis de collaborer avec des personnes extérieures à votre organisation, Microsoft Teams vous propose deux options :

- **Accès externe** : type de fédération qui permet aux utilisateurs de rechercher, d’appeler des personnes d’autres organisations, puis de discuter avec elles. Vous ne pouvez pas ajouter ces personnes à des équipes, sauf en tant qu’invitées.
- **Accès invité** : l’accès invité vous permet d’inviter des personnes extérieures à votre organisation à rejoindre une équipe. Les personnes invitées obtiennent un compte invité dans Azure Active Directory.

Note : Teams vous permet d’inviter des personnes extérieures à votre organisation à des réunions. Cela ne nécessite pas de configuration de l’accès externe ou invité.

## <a name="external-access-federation"></a>Accès externe (fédération)

Configurez l’accès externe si vous avez besoin de rechercher, d’appeler, de discuter, puis de configurer des réunions avec des personnes extérieures à votre organisation qui utilisent Teams, Skype Entreprise (en ligne ou en local) ou Skype. 

Par défaut, l'accès externe est activé pour tous les domaines. Vous pouvez restreindre l’accès externe en autorisant ou en bloquant des domaines spécifiques, ou en le désactivant.

![Capture d’écran des paramètres d’accès externe](media/external-access-federation-settings.png)

Si vous souhaitez configurer l’accès externe, veuillez consulter la rubrique [Gérer l'accès externe](manage-external-access.md). 

>[!NOTE]
>Les licences gratuites Microsoft Teams ne prisent pas en charge l’accès externe.

## <a name="guest-access"></a>Accès invité

L’accès invité permet d’ajouter une personne extérieure à votre organisation à une équipe, dans laquelle elle peut discuter, appeler, rencontrer des participants, puis collaborer sur des fichiers. Les invités peuvent bénéficier de presque toutes les mêmes fonctionnalités Teams que les membres d’équipe natifs.

Les invités sont ajoutés au répertoire Azure Active Directory de votre organisation en tant qu’utilisateurs B2B, puis doivent se connecter à Teams à l’aide de leur compte invité. En d’autres termes, ils devront sans doute se déconnecter de leurs propres organisations pour se connecter à la vôtre.

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

<sup>1</sup> À condition que l’utilisateur ait été ajouté en tant qu’invité et soit connecté avec le compte invité.<br>
<sup>2</sup> Uniquement par adresse e-mail ou SIP (Session Initiation Protocol).<br>
<sup>3</sup> Fonction prise en charge pour la conversation 1:1 entre utilisateurs Teams uniquement de deux organisations différentes. <br>
<sup>4</sup> Par défaut, les participants externes n’ont pas accès aux numéros de téléphone des participants distants. Si vous voulez conserver la confidentialité de ces numéros de téléphone, sélectionnez **Tonalités** pour le **type d’annonce d’entrée/sortie** (cela permet d’éviter que les numéros soient lus par les équipes). Pour plus d’informations, voir [Activer ou désactiver l’entrée et quitter les annonces pour les réunions dans Microsoft teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md). <br>
<sup>5</sup> Fonction autorisée par défaut, mais l’administrateur Teams peut la désactiver

## <a name="related-topics"></a>Voir aussi

[Accès externe dans Teams](manage-external-access.md)

[Accès invité dans Teams](guest-access.md)
