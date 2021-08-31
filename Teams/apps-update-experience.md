---
title: Expérience de mise à jour des applications dans Microsoft Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 0755c505a25d4c858afd104331d193edd8b2b27c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726203"
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

## <a name="related-topics"></a>Sujets associés

[Gérer les applications](manage-apps.md)
