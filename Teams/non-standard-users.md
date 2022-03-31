---
title: Teams comportement des applications en fonction des types d’utilisateurs
author: guptaashish
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez le comportement des applications Microsoft Teams’application pour différents types d’utilisateurs.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe3ad067844de3c7a5dda0a042dee837a9638eae
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556285"
---
# <a name="microsoft-teams-apps-behavior-based-on-types-of-users"></a>Microsoft Teams comportement des applications en fonction des types d’utilisateurs

Teams les applications se comportent quand des utilisateurs invités, externes (fédérés) et anonymes sont présents dans un Teams contexte.

- Un **utilisateur invité est** une personne qui n’est ni un employé, ni un étudiant ni un membre de votre organisation. Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation.

- Un **utilisateur externe (fédéré)** appartient à un autre domaine et n’a pas accès aux équipes ou ressources d’équipe de votre organisation.

  > [!Note]
  > Pour une comparaison plus détaillée des utilisateurs invités et externes, voir [Communiquer avec des utilisateurs d’autres organisations](./communicate-with-users-from-other-organizations.md).

- Un **utilisateur anonyme est** un concept qui existe Teams réunions au cours des laquelle l’utilisateur a rejoint la réunion via un lien. L’utilisateur n’est pas connecté avec son compte Microsoft ou le compte de son organisation.

## <a name="guest-users"></a>Utilisateurs invités

### <a name="install-update-and-delete-for-guest-users"></a>Installer, mettre à jour et supprimer des utilisateurs invités

Les invités ne peuvent pas installer, mettre à jour ou supprimer des applications dans un contexte partagé, tel qu’une conversation, un canal ou une réunion, mais ils peuvent l’avoir dans leur étendue personnelle à l’aide d’extensions de messages et de liens directs. Les invités n’ont pas accès à l’App Store Teams à partir de l’application de bureau Teams, mais ils peuvent y accéder à l’aide d’un lien direct.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Comportement et stratégie d’utilisation pour les utilisateurs invités

Les invités peuvent utiliser une application si l’application a été installée par un utilisateur natif.

#### <a name="bots-installed-to-a-channel"></a>Bots installed to a channel

Les utilisateurs invités peuvent mentionner le robot et interagir avec les cartes adaptatives.

#### <a name="personal-bots-installed-with-policies"></a>Bots personnels installés avec des stratégies

- Les invités respecteront les stratégies d’autorisation globales et à l’échelle de l’organisation définies pour le client hôte pour n’importe quelle application. Si une application est bloquée pour l’ensemble de l’organisation hôte, les invités ne peuvent pas non plus l’utiliser.
- Les robots inclus dans la stratégie de configuration d’application par défaut globale sont également installés pour les invités.
- Une fois qu’un bot est installé, les robots peuvent communiquer de façon proactive avec les invités et les invités peuvent communiquer avec les robots.
- Vous ne pouvez pas supprimer un invité de la stratégie de configuration globale par défaut de l’application.
- Pour éviter que les invités accèdent aux bots, vous pouvez créer d’autres stratégies de configuration d’application, les affecter à des utilisateurs internes et installer des bots avec les stratégies personnalisées.

## <a name="external-federated-users"></a>Utilisateurs externes (fédérés)

### <a name="install-update-and-delete-for-external-users"></a>Installer, mettre à jour et supprimer des utilisateurs externes

Les utilisateurs externes ne peuvent pas installer, mettre à jour ou supprimer des applications dans n’importe quel contexte, tel qu’une conversation personnelle, un canal ou une réunion. Ils n’ont pas accès au magasin d Teams apps de l’organisation d’hébergement.

### <a name="usage-behavior-and-policy-for-external-users"></a>Comportement et stratégie d’utilisation pour les utilisateurs externes

- Les membres d’autres organisations respectent la stratégie globale (à l’échelle de l’organisation par défaut) de l’organisation d’hébergement
- Les utilisateurs de l’organisation d’hébergement peuvent ajouter des applications aux conversations de réunion avec des personnes d’autres organisations. Les utilisateurs d’autres organisations ne peuvent pas ajouter d’applications dans les conversations de réunion, mais peuvent interagir avec des bots, des onglets et des extensions de message une fois ajoutés à la conversation.
- Une fois qu’un robot est installé dans une conversation de réunion, il peut communiquer de façon proactive avec les personnes d’autres organisations au cours de cette conversation et ces personnes peuvent communiquer avec le robot.
- Les stratégies de données de l’organisation d’hébergement, ainsi que les pratiques de partage de données des applications tierces partagées par l’organisation de cet utilisateur, sont appliquées.

## <a name="anonymous-users"></a>Utilisateurs anonymes

### <a name="install-update-and-delete-for-anonymous-users"></a>Installation, mise à jour et suppression pour les utilisateurs anonymes

Les utilisateurs anonymes ne peuvent pas installer, mettre à jour ou supprimer des applications dans les réunions.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportement et stratégie d’utilisation pour les utilisateurs anonymes

Les utilisateurs anonymes ne peuvent pas utiliser directement des applications dans les réunions. Les utilisateurs natifs peuvent continuer à utiliser les applications de réunion si des utilisateurs anonymes sont présents. Si une application envoie une carte adaptative dans la conversation, les utilisateurs anonymes peuvent interagir avec la carte. Pour plus d’informations, voir [Autoriser les utilisateurs anonymes à participer à des réunions](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).

Les utilisateurs anonymes héritent de la stratégie d’autorisation globale par défaut au niveau utilisateur. Ils peuvent interagir avec les applications dans Teams réunions si la stratégie d’autorisation au niveau utilisateur a activé l’application. Les utilisateurs anonymes peuvent uniquement interagir avec les applications déjà disponibles dans une réunion et qui ne peuvent pas acquérir et/ou gérer ces applications.

## <a name="related-topics"></a>Sujets associés

[Gérer les stratégies de mise en application dans Microsoft Teams](teams-app-setup-policies.md)
