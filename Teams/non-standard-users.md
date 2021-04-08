---
title: Comportement des applications Teams pour les utilisateurs non standard
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez le comportement des applications dans Microsoft Teams pour les utilisateurs non standard.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb4b5dfebabfcd0bc86006d93272c3901e7dcfc7
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617847"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Comportement des applications Microsoft Teams pour les utilisateurs non standard

Cet article décrit le comportement des applications dans Teams lorsque des utilisateurs invités, externes (fédérés) et anonymes sont présents dans un contexte Teams.

- Un **utilisateur invité est** une personne qui n’est ni un employé, ni un étudiant ni un membre de votre organisation. Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation.

- Un **utilisateur externe (fédéré)** appartient à un autre domaine et n’a pas accès aux équipes ou ressources d’équipe de votre organisation.

  > [!Note]
  > Pour une comparaison plus détaillée des utilisateurs invités et externes, voir [Communiquer avec des utilisateurs d’autres organisations.](./communicate-with-users-from-other-organizations.md)

- Un **utilisateur anonyme est** un concept dans les réunions Teams où l’utilisateur a rejoint la réunion via un lien. L’utilisateur n’est pas connecté avec son compte Microsoft ou celui de son organisation.

## <a name="guest-user-access"></a>Accès des utilisateurs invités

### <a name="install-update-and-delete-for-guest-users"></a>Installer, mettre à jour et supprimer des utilisateurs invités

Les invités ne peuvent pas installer, mettre à jour ou supprimer des applications dans un contexte partagé, tel qu’une conversation, un canal ou une réunion. Ils peuvent installer, mettre à jour ou supprimer des applications dans leur étendue personnelle à l’aide d’extensions de messages et de liens directs. Les invités n’ont pas accès au magasin d’applications Teams.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Comportement et stratégie d’utilisation pour les utilisateurs invités

Les invités peuvent utiliser une application si l’application a été installée par un utilisateur natif.

Les robots peuvent envoyer un message de façon proactive aux utilisateurs invités, mais les invités ne peuvent pas interagir avec le robot. Les invités ne peuvent pas envoyer de message au bot 1:1, @mentionner le robot ou interagir avec des cartes adaptatives qui communiquent avec le bot.

Les invités respecteront les stratégies d’autorisation globales et à l’échelle de l’organisation définies pour le client hôte pour n’importe quelle application. En d’autres termes, si une application est bloquée pour l’ensemble de l’organisation hôte, les invités ne peuvent pas non plus l’utiliser.

Les stratégies d’installation ne s’appliquent pas aux utilisateurs invités. Cela signifie que l’application épinglée par l’administrateur à partir de la stratégie par défaut n’affecte pas les utilisateurs invités.

## <a name="external-federated-user-access"></a>Accès des utilisateurs externes (fédérés)

### <a name="install-update-and-delete-for-external-users"></a>Installer, mettre à jour et supprimer des utilisateurs externes

Les utilisateurs externes ne peuvent pas installer, mettre à jour ou supprimer des applications dans n’importe quel contexte, tel qu’une conversation personnelle, un canal ou une réunion. Ils n’ont pas accès au magasin d’applications Teams.

### <a name="usage-behavior-and-policy-for-external-users"></a>Comportement et stratégie d’utilisation pour les utilisateurs externes

Les utilisateurs externes ne peuvent pas utiliser les applications Teams et, lorsqu’un utilisateur externe est ajouté à un contexte avec des utilisateurs natifs, tous les utilisateurs, natifs et externes, ne peuvent plus utiliser d’applications.

Les utilisateurs externes ne sont pas impactés par les stratégies d’application, car ils ne peuvent pas utiliser les applications Teams.

## <a name="anonymous-user-in-meetings-access"></a>Utilisateur anonyme dans l’accès aux réunions

### <a name="install-update-and-delete-for-anonymous-users"></a>Installation, mise à jour et suppression pour les utilisateurs anonymes

Les utilisateurs anonymes ne peuvent pas installer, mettre à jour ou supprimer des applications dans les réunions.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportement et stratégie d’utilisation des utilisateurs anonymes

Les utilisateurs anonymes ne peuvent pas utiliser directement des applications dans les réunions. Les utilisateurs natifs peuvent continuer à utiliser les applications de réunion si des utilisateurs anonymes sont présents. Si une application envoie une carte adaptative dans la conversation, les utilisateurs anonymes peuvent interagir avec la carte pour plus d’informations, voir Autoriser les utilisateurs anonymes à [participer à des réunions.](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)

Les utilisateurs anonymes héritent de la stratégie d’autorisation globale par défaut au niveau utilisateur. Ils peuvent interagir avec des applications dans les réunions Teams si la stratégie d’autorisation au niveau utilisateur a activé l’application. Les utilisateurs anonymes peuvent uniquement interagir avec les applications déjà disponibles dans une réunion et qui ne peuvent pas acquérir et/ou gérer ces applications.
