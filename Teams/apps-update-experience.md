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
description: Découvrez comment mettre à jour des applications dans Microsoft Teams.
ms.openlocfilehash: 7139fb1f1788ff0e9fe093a17fbe08842f47bfd9
ms.sourcegitcommit: b8098d6ea36f10ee3a630a230ebd84bc2d96e37a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/31/2022
ms.locfileid: "65780610"
---
# <a name="update-apps-in-microsoft-teams"></a>Mettre à jour des applications dans Microsoft Teams

Dans la plupart des cas, une fois que les développeurs d’applications publient une mise à jour d’application, la nouvelle version s’affiche automatiquement pour les utilisateurs. Toutefois, certaines mises à jour du [manifeste Microsoft Teams](/microsoftteams/platform/resources/schema/manifest-schema) nécessitent l’acceptation de l’utilisateur :

* Un bot a été ajouté ou supprimé
* Modification de la propriété « botId » d’un bot existant
* Modification de la propriété « isNotificationOnly » d’un bot existant
* La fonctionnalité SupportsCalling, SupportsVideo et SupportsFiles d’un bot a été ajoutée
* Une extension de messagerie a été ajoutée
* Un nouveau connecteur a été ajouté
* Des autorisations dans « Authorization » ont été ajoutées ou modifiées

![nouvelle version disponible.](media/manage-your-custom-apps-update1.png)

![option de mise à niveau pour une application.](media/manage-your-custom-apps-update2.png)

> [!NOTE]
> Le processus de mise à jour s’applique à toutes les mises à jour d’application pour les applications Microsoft, les applications personnalisées et les applications tierces.
