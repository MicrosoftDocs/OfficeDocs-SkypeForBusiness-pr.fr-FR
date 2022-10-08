---
title: Disponibilité et utilisation des applications Teams par différents types d’utilisateurs
author: ashishguptaiitb
ms.author: guptaashish
ms.reviewer: kojika
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: Découvrez comment les applications dans Microsoft Teams fonctionnent pour les invités, les utilisateurs fédérés et les utilisateurs anonymes.
ms.localizationpriority: high
ms.date: 09/28/2022
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fa9b56a17cdba5bfe4b075199a3373470d1630a
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494627"
---
# <a name="use-teams-apps-as-an-external-attendees-or-guest"></a>Utiliser des applications Teams en tant que participants externes ou invités

Les applications Teams permettent la collaboration avec des personnes extérieures à votre organisation. En tant qu’administrateur, vous contrôlez qui peut accéder aux conversations, aux réunions et au canal Teams pour collaborer avec les utilisateurs de votre organisation. Pour plus d’informations, découvrez [comment autoriser la collaboration avec les participants externes](manage-external-access.md) et [ce que les invités peuvent faire dans Teams](guest-access.md). Cet article se concentre sur l’utilisation d’applications par des personnes extérieures à votre organisation.

Les types d’utilisateurs suivants peuvent être présents dans une conversation ou une réunion Teams et, si vous l’autorisez, ils peuvent utiliser des applications dans Teams.

* Un **utilisateur invité** est une personne qui n’est pas un employé, un étudiant ou un membre de votre organisation. Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation.

* Un **utilisateur externe (fédéré)** est issu d’un autre domaine et n’a pas accès aux ressources Teams de votre organisation.

* Un **utilisateur anonyme** est un utilisateur qui rejoint une réunion via un lien. L’utilisateur n’est pas connecté avec son compte Microsoft ou le compte de son organisation.

Pour obtenir une comparaison plus détaillée entre les utilisateurs invités et externes, consultez [communiquer avec les utilisateurs d’autres organisations](communicate-with-users-from-other-organizations.md).

## <a name="guests"></a>Invités

### <a name="install-update-and-delete-apps-for-guests"></a>Installer, mettre à jour et supprimer des applications pour les invités

Les invités ne peuvent pas installer, mettre à jour ou supprimer des applications dans un contexte partagé, tel qu’une conversation, un canal ou une réunion. Les invités peuvent le faire dans leur étendue personnelle à l’aide d’extensions de message et de liens directs. Les invités ne peuvent pas accéder à l’App Store Teams à partir de l’application de bureau Teams, mais ils peuvent y accéder avec un lien direct.

### <a name="usage-behavior-and-policy-for-guests"></a>Comportement et stratégie d’utilisation pour les invités

Les invités peuvent utiliser une application si l’application a été installée par l’utilisateur d’une organisation.

#### <a name="bots-installed-to-a-channel"></a>Bots installés sur un canal

Les invités peuvent mentionner le bot et interagir avec les cartes adaptatives.

#### <a name="personal-bots-installed-with-policies"></a>Bots personnels installés avec des stratégies

* Pour n’importe quelle application, les invités respectent les stratégies d’autorisation globales et à l’échelle de l’organisation définies pour l’organisation hôte. Si une application est bloquée pour l’ensemble de l’organisation hôte, les invités ne peuvent pas non plus utiliser l’application.
* Tout bot inclus dans la stratégie d’installation d’application par défaut globale sera également installé pour les invités.
* Une fois qu’un bot est installé, les bots et les invités peuvent communiquer de manière proactive les uns avec les autres.
* Vous ne pouvez pas supprimer un invité de la stratégie d’installation d’application par défaut globale.
* Pour éviter que l’invité n’accède aux bots, vous pouvez créer d’autres stratégies d’installation d’application, les affecter à des utilisateurs internes et installer des bots avec les stratégies personnalisées.

## <a name="federated-users"></a>Utilisateurs fédérés

### <a name="install-update-and-delete-apps-for-federated-users"></a>Installer, mettre à jour et supprimer des applications pour les utilisateurs fédérés

Les utilisateurs fédérés ne peuvent pas installer, mettre à jour ou supprimer des applications dans n’importe quel contexte, tel qu’une réunion, une conversation, un canal ou une réunion. Ils n’ont pas accès à l’App Store Teams de l’organisation d’hébergement.

### <a name="usage-behavior-and-policy-for-federated-users"></a>Comportement et stratégie d’utilisation pour les utilisateurs fédérés

* Personnes d’autres organisations adhèrent à la stratégie globale de l’organisation d’hébergement (par défaut à l’échelle de l’organisation)
* Les utilisateurs de l’organisation d’hébergement peuvent ajouter des applications dans des conversations de réunion avec des personnes d’autres organisations. Personnes d’autres organisations ne peuvent pas ajouter d’applications dans des conversations de réunion, mais peuvent interagir avec des bots, des onglets et des extensions de message une fois ajoutés à la conversation.
* Une fois qu’un bot est installé dans une conversation de réunion, il peut communiquer de manière proactive avec des personnes d’autres organisations dans cette conversation, et ces personnes peuvent communiquer avec le bot.
* Les stratégies de données de l’organisation d’hébergement sont appliquées.
* Les pratiques de partage de données de toutes les applications tierces partagées par l’organisation de cet utilisateur sont appliquées.

## <a name="anonymous-users"></a>Utilisateurs anonymes

### <a name="install-update-and-delete-apps-for-anonymous-users"></a>Installer, mettre à jour et supprimer des applications pour les utilisateurs anonymes

Les utilisateurs anonymes ne peuvent pas installer, mettre à jour ou supprimer des applications dans des réunions.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportement et stratégie d’utilisation pour les utilisateurs anonymes

Les utilisateurs anonymes ne peuvent pas utiliser directement des applications dans les réunions. Si une application envoie une carte adaptative dans la conversation, les utilisateurs anonymes peuvent interagir avec la carte. Ces utilisateurs peuvent interagir avec les applications dans les réunions Teams si la stratégie d’autorisation au niveau de l’utilisateur active l’application. Les utilisateurs anonymes héritent de la stratégie d’autorisation par défaut globale au niveau de l’utilisateur.

Les utilisateurs anonymes peuvent interagir uniquement avec les applications qui sont déjà disponibles dans une réunion, mais ne peuvent pas acquérir et gérer ces applications. Les utilisateurs natifs peuvent continuer à utiliser les applications de réunion même lorsque les utilisateurs anonymes participent à une réunion.

### <a name="disallow-anonymous-users-to-use-apps-in-meetings"></a>Interdire aux utilisateurs anonymes d’utiliser des applications dans des réunions

Par défaut, les utilisateurs anonymes peuvent interagir avec les applications existantes dans une réunion. Vous pouvez interdire aux utilisateurs anonymes d’interagir avec des applications.

1. Connectez-vous au Centre d’administration Teams et accédez aux **[paramètres de réunions](https://admin.teams.microsoft.com/meetings/settings)** > .

1. Sous **Participants**, modifiez le bouton bascule pour **que les utilisateurs anonymes puissent interagir avec les applications dans les réunions** sur **Désactivé**.

1. Sélectionnez **Enregistrer**.

## <a name="related-articles"></a>Articles connexes

* [Autoriser les utilisateurs anonymes à participer à des réunions](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Gérer les stratégies d’installation des applications dans Microsoft Teams](teams-app-setup-policies.md).
* [Comment permettre la collaboration avec les invités et les participants externes](manage-external-access.md).
* [Que peuvent faire les invités dans Teams ?](guest-access.md)
