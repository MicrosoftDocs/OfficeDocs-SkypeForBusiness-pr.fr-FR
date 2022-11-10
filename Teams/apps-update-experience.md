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
ms.date: 10/22/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Dans cet article, découvrez comment les applications Microsoft, les applications personnalisées et les applications tierces dans Microsoft Teams sont mises à jour et comment les administrateurs les mettent à disposition.
ms.openlocfilehash: d419e1ed29c6a1cd7a7390bdc0d5eb69371d8547
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912793"
---
# <a name="role-of-an-admin-in-upgrading-teams-apps"></a>Rôle d’un administrateur dans la mise à niveau des applications Teams

Les administrateurs Teams peuvent aider leurs utilisateurs finaux à obtenir la dernière version des applications. Pour ce faire, ils effectuent l’une des tâches suivantes ou les deux :

* [Mettez à jour les applications tierces](#updates-to-third-party-apps) disponibles dans le Magasin Teams lorsqu’une nouvelle version est fournie par le développeur ou le fournisseur de l’application.
* [Mettez à jour les applications personnalisées](#updates-to-custom-apps) qui sont disponibles uniquement dans votre organisation lorsque votre développeur envoie une nouvelle version.

## <a name="updates-to-third-party-apps"></a>Mises à jour à des applications tierces

Pour que les utilisateurs installent et utilisent une application, ils doivent accorder des autorisations à l’application pour accéder aux services et aux informations requis. Dans la plupart des cas, lorsqu’une nouvelle version d’une application installée est disponible dans le magasin Teams, l’application est automatiquement mise à jour pour tous les utilisateurs. Toutefois, quelques modifications spécifiques apportées à la nouvelle version de l’application nécessitent à nouveau une autorisation utilisateur. Cette acceptation répétée de l’utilisateur garantit la connaissance des modifications telles que les fonctionnalités ou l’accès aux informations personnelles. Les administrateurs Teams peuvent [fournir des autorisations à une application au nom des utilisateurs](app-permissions-admin-center.md).

Si les développeurs d’applications apportent une ou plusieurs modifications suivantes à leurs applications, les utilisateurs finaux doivent approuver la mise à jour de l’application.

* Ajoutez un bot. Modifiez l’ID du bot à l’aide de la `botId` propriété .
* Modifiez la `isNotificationOnly` propriété d’un bot existant qui peut modifier les notifications du bot.
* Modifiez `SupportsCalling`les propriétés , `SupportsVideo`et `SupportsFiles` d’un bot existant pour ajouter des fonctionnalités d’appel, de lecture de vidéo et de chargement ou de téléchargement de fichiers.
* Ajouter ou supprimer des autorisations dans l’autorisation.
* Ajoutez ou supprimez une extension de messagerie, ajoutez un onglet de groupe, ajoutez un connecteur ou ajoutez un canal.
* Modifiez les paramètres dans dans [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) le fichier manifeste.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>Mises à jour aux applications personnalisées

Les applications personnalisées créées et déployées au sein de votre organisation sont accessibles aux utilisateurs de votre locataire ou de votre organisation. L’administrateur Teams met à jour une application personnalisée vers sa nouvelle version lorsqu’une nouvelle version est fournie par les développeurs de son organisation. Pour plus d’informations, consultez [comment les administrateurs gèrent les applications personnalisées](custom-app-overview.md).

## <a name="related-articles"></a>Articles connexes

* [Comprendre le schéma du manifeste pour les mises à jour effectuées dans les applications](/microsoftteams/platform/resources/schema/manifest-schema).
* [En savoir plus sur la gestion des applications personnalisées](custom-app-overview.md).
