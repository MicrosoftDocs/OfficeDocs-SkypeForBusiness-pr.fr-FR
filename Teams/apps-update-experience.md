---
title: Expérience de mise à jour d’applications dans Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
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
ms.openlocfilehash: ed91ad441b773833838796d9ea8c71038c842b88
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299043"
---
# <a name="update-apps-in-microsoft-teams"></a>Mettre à jour des applications dans Microsoft Teams

Dans la plupart des cas, une fois qu’une nouvelle version d’une application est disponible dans Teams Store, l’application est automatiquement mise à jour pour les utilisateurs. Toutefois, quelques modifications spécifiques apportées à la nouvelle version de l’application nécessitent l’acceptation par l’utilisateur de la mise à jour de l’application. L’acceptation de l’utilisateur garantit la sensibilisation aux modifications telles que les fonctionnalités ou l’accès. Si les développeurs d’applications apportent les modifications spécifiques suivantes aux applications Microsoft Teams, vos utilisateurs finaux doivent approuver la mise à jour de l’application :

* Un bot est ajouté.
* La propriété `isNotificationOnly` d’un bot existant ou la propriété `botId` est modifiée.
* La fonctionnalité `SupportsCalling`, `SupportsVideo` ou `SupportsFiles` d’un bot est ajoutée.
* Une extension de messagerie a été ajoutée.
* Les autorisations dans Autorisation sont ajoutées ou modifiées.
* `Id` ou `ApplicationPermissionsHash`, ou les deux sont modifiés à l’intérieur du `webApplicationInfo`.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="related-articles"></a>Articles connexes

* [Comprendre le schéma du manifeste pour les mises à jour effectuées dans les applications](/microsoftteams/platform/resources/schema/manifest-schema).
