---
title: Expérience de mise à jour d’applications dans Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Dans cet article, découvrez comment les applications Microsoft, les applications personnalisées et les applications tierces dans Microsoft Teams sont mises à jour et comment les administrateurs les mettent à disposition.
ms.openlocfilehash: 3d0264a31214b51e751d52ffe90411f227e46656
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837534"
---
# <a name="teams-app-updates-and-admin-role"></a>Mises à jour d’application Teams et rôle d’administrateur

Les administrateurs Teams peuvent aider leurs utilisateurs finaux à obtenir la dernière version des applications. Pour ce faire, ils effectuent une ou les deux tâches suivantes :

* [Mettez à jour les applications tierces](#updates-to-third-party-apps) qui sont disponibles dans le magasin Teams lorsqu’une nouvelle version est fournie par le développeur ou le fournisseur de l’application.
* [Mettez à jour les applications personnalisées](#updates-to-custom-apps) qui sont disponibles uniquement dans votre organisation lorsque votre développeur soumet une nouvelle version.

## <a name="updates-to-third-party-apps"></a>Mises à jour à des applications tierces

Pour que les utilisateurs installent et utilisent une application, ils doivent accorder des autorisations à l’application pour accéder aux services et informations requis. Dans la plupart des cas, lorsqu’une nouvelle version d’une application installée est disponible dans le Magasin Teams, l’application est automatiquement mise à jour pour tous les utilisateurs. Toutefois, quelques modifications spécifiques apportées à la nouvelle version de l’application nécessitent à nouveau une autorisation utilisateur. Cette acceptation répétée de l’utilisateur garantit une prise de conscience des modifications telles que les fonctionnalités ou l’accès aux informations personnelles. Les administrateurs Teams peuvent [fournir des autorisations à une application pour le compte des utilisateurs](app-permissions-admin-center.md).

Si les développeurs d’applications apportent une ou plusieurs modifications suivantes à leurs applications, les utilisateurs finaux doivent approuver la mise à jour de l’application.

* Ajoutez ou supprimez un bot. Modifiez l’ID du bot à l’aide de la `botId` propriété.
* Modifiez la `isNotificationOnly` propriété d’un bot existant qui peut modifier les notifications du bot.
* Modifiez `SupportsCalling`, `SupportsVideo`et `SupportsFiles` les propriétés d’un bot existant pour ajouter la fonctionnalité d’appel, de lecture de vidéo et de chargement ou de téléchargement de fichiers.
* Ajoutez ou supprimez des autorisations dans l’autorisation.
* Ajoutez ou supprimez une extension de messagerie, ajoutez un onglet de groupe, ajoutez un connecteur ou ajoutez un canal.
* Modifiez les paramètres dans le [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) fichier manifeste.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>Mises à jour aux applications personnalisées

Les applications personnalisées créées et déployées au sein de votre organisation sont disponibles pour les utilisateurs de votre locataire ou organisation. L’administrateur Teams met à jour les applications personnalisées vers les nouvelles versions fournies par les développeurs au sein de l’organisation. Pour plus d’informations, consultez [la façon dont les administrateurs gèrent les applications personnalisées](custom-app-overview.md).

## <a name="related-article"></a>Article connexe

* [Comprendre le schéma du manifeste pour les mises à jour effectuées dans les applications](/microsoftteams/platform/resources/schema/manifest-schema).
* [En savoir plus sur la gestion des applications personnalisées](custom-app-overview.md).
