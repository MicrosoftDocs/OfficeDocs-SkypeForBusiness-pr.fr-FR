---
title: Expérience de mise à jour des applications dans Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Dans cet article, découvrez comment les applications Microsoft, les applications personnalisées et les applications tierces dans Microsoft Teams sont mises à jour.
ms.openlocfilehash: 27d51a487af918e6fcee2b7806c81d31506bd1af
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958039"
---
# <a name="update-apps-in-microsoft-teams"></a>Mettre à jour des applications dans Microsoft Teams

Dans la plupart des cas, une fois que les développeurs d’applications publient une mise à jour d’application, la nouvelle version s’affiche automatiquement pour les utilisateurs. Toutefois, certaines mises à jour du [manifeste Microsoft Teams](/microsoftteams/platform/resources/schema/manifest-schema) nécessitent l’acceptation de l’utilisateur :

* Un bot a été ajouté ou supprimé.
* La propriété « botId » d’un bot existant a changé.
* La propriété « isNotificationOnly » d’un bot existant a changé.
* La fonctionnalité SupportsCalling, SupportsVideo et SupportsFiles d’un bot a été ajoutée.
* Une extension de messagerie a été ajoutée.
* Un nouveau connecteur a été ajouté.
* Des autorisations dans « Authorization » ont été ajoutées ou modifiées.

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="Nouvelle version disponible." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Option de mise à niveau pour une application." lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> Le processus de mise à jour s’applique à toutes les mises à jour d’application pour les applications Microsoft, les applications personnalisées et les applications tierces.
