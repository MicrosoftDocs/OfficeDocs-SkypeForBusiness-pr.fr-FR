---
title: Expérience de mise à jour des applications dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
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
description: Découvrez comment mettre à jour les applications dans Microsoft Teams.
ms.openlocfilehash: bcece8d3b6da3f0e89694b29d61752634ea1bc18
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62409867"
---
# <a name="update-apps-in-microsoft-teams"></a>Mettre à jour des applications dans Microsoft Teams

Dans la plupart des cas, une fois que les développeurs d’applications publient une mise à jour d’application, la nouvelle version s’affiche automatiquement pour les utilisateurs. Toutefois, certaines mises à jour du manifeste <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams</a> nécessitent l’acceptation des utilisateurs :

* Un robot a été ajouté ou supprimé
* La propriété « botId » d’un robot existant a été modifiée
* La propriété « isNotificationOnly » d’un robot existant a été modifiée
* Les fonctionnalités SupportCalling, SupportsVideo et SupportsFiles d’un robot ont été ajoutées
* Une extension de messagerie a été ajoutée
* Un nouveau connecteur a été ajouté
* Propriétés dans « webApplicationInfo » modifiées

![nouvelle version disponible.](media/manage-your-custom-apps-update1.png)

![option de mise à niveau pour une application.](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> Le processus de mise à jour s’applique à toutes les mises à jour d’application pour les applications Microsoft, les applications personnalisées et les applications tierces. 

## <a name="related-topics"></a>Voir aussi

[Gérer les applications](manage-apps.md)
