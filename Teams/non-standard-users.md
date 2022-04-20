---
title: Teams le comportement des applications en fonction des types d’utilisateurs
author: guptaashish
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment les applications dans Microsoft Teams se comportent pour différents types d’utilisateurs.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a407564986d5e4c758d39e2684e5c068539bb9dc
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922465"
---
# <a name="microsoft-teams-apps-behavior-based-on-types-of-users"></a>Microsoft Teams le comportement des applications en fonction des types d’utilisateurs

Teams applications se comportent lorsque des utilisateurs invités, externes (fédérés) et anonymes sont présents dans un contexte Teams.

* Un **utilisateur invité** est une personne qui n’est pas un employé, un étudiant ou un membre de votre organisation. Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation.

* Un **utilisateur externe (fédéré)** appartient à un autre domaine et n’a pas accès aux équipes ou ressources d’équipe de votre organisation.

  > [!Note]
  > Pour obtenir une comparaison plus détaillée des utilisateurs invités et externes, [consultez communiquer avec les utilisateurs d’autres organisations](./communicate-with-users-from-other-organizations.md).

* Un **utilisateur anonyme** est un concept dans Teams réunions où l’utilisateur a rejoint la réunion via un lien. L’utilisateur ne s’est pas connecté avec son compte Microsoft ou organisation.

## <a name="guest-users"></a>Utilisateurs invités

### <a name="install-update-and-delete-for-guest-users"></a>Installer, mettre à jour et supprimer pour les utilisateurs invités

Les invités ne peuvent pas installer, mettre à jour ou supprimer des applications dans un contexte partagé, tel qu’une conversation, un canal ou une réunion, mais ils peuvent accéder à leur étendue personnelle à l’aide d’extensions de message et de liens directs. Les invités n’ont pas accès à l’app store Teams à partir de l’application de bureau Teams, mais ils peuvent y accéder avec un lien direct.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Comportement et stratégie d’utilisation pour les utilisateurs invités

Les invités peuvent utiliser une application si l’application a été installée par un utilisateur natif.

#### <a name="bots-installed-to-a-channel"></a>Bots installés sur un canal

Les utilisateurs invités peuvent mentionner le bot et interagir avec les cartes adaptatives.

#### <a name="personal-bots-installed-with-policies"></a>Bots personnels installés avec des stratégies

* Les invités adhèrent aux stratégies d’autorisation globales et à l’échelle de l’organisation définies pour le locataire hôte pour n’importe quelle application. Si une application est bloquée pour l’ensemble de l’organisation hôte, les invités ne peuvent pas non plus utiliser l’application.
* Tout bot inclus dans la stratégie d’installation d’application par défaut globale sera également installé pour les invités.
* Une fois qu’un bot est installé, les bots peuvent communiquer de manière proactive avec les invités et les invités peuvent communiquer avec les bots.
* Vous ne pouvez pas supprimer un invité de la stratégie d’installation d’application par défaut globale.
* Pour éviter que l’invité n’accède aux bots, vous pouvez créer d’autres stratégies d’installation d’application, les affecter à des utilisateurs internes et installer des bots avec les stratégies personnalisées.

## <a name="external-federated-users"></a>Utilisateurs externes (fédérés)

### <a name="install-update-and-delete-for-external-users"></a>Installer, mettre à jour et supprimer pour les utilisateurs externes

Les utilisateurs externes ne peuvent pas installer, mettre à jour ou supprimer des applications dans n’importe quel contexte, tel qu’une réunion, une conversation, un canal ou une réunion. Ils n’ont pas accès à l’app store Teams de l’organisation d’hébergement.

### <a name="usage-behavior-and-policy-for-external-users"></a>Comportement et stratégie d’utilisation pour les utilisateurs externes

* Les personnes d’autres organisations adhèrent à la stratégie globale de l’organisation d’hébergement (par défaut à l’échelle de l’organisation)
* Les utilisateurs de l’organisation d’hébergement peuvent ajouter des applications dans des conversations de réunion avec des personnes d’autres organisations. Les personnes d’autres organisations ne peuvent pas ajouter d’applications dans des conversations de réunion, mais peuvent interagir avec des bots, des onglets et des extensions de message une fois ajoutés à la conversation.
* Une fois qu’un bot est installé dans une conversation de réunion, il peut communiquer de manière proactive avec des personnes d’autres organisations dans cette conversation et ces personnes peuvent communiquer avec le bot.
* Les stratégies de données de l’organisation d’hébergement, ainsi que les pratiques de partage de données de toutes les applications tierces partagées par l’organisation de cet utilisateur, sont appliquées.

## <a name="anonymous-users"></a>Utilisateurs anonymes

### <a name="install-update-and-delete-for-anonymous-users"></a>Installer, mettre à jour et supprimer pour les utilisateurs anonymes

Les utilisateurs anonymes ne peuvent pas installer, mettre à jour ou supprimer des applications dans des réunions.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportement et stratégie d’utilisation pour les utilisateurs anonymes

Les utilisateurs anonymes ne peuvent pas utiliser directement des applications dans les réunions. Les utilisateurs anonymes héritent de la stratégie d’autorisation par défaut globale au niveau de l’utilisateur. Si une application envoie une carte adaptative dans la conversation, les utilisateurs anonymes peuvent interagir avec la carte. Ces utilisateurs peuvent interagir avec des applications dans Teams réunions si la stratégie d’autorisation au niveau de l’utilisateur active l’application.

Les utilisateurs anonymes peuvent uniquement interagir avec les applications qui sont déjà disponibles dans une réunion et ne peuvent pas acquérir et gérer ces applications. Les utilisateurs natifs peuvent continuer à utiliser les applications de réunion même lorsque les utilisateurs anonymes participent à une réunion.

## <a name="see-also"></a>Voir aussi

* [Autoriser les utilisateurs anonymes à participer à des réunions](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Gérer les stratégies d’installation d’application dans Microsoft Teams](teams-app-setup-policies.md).
