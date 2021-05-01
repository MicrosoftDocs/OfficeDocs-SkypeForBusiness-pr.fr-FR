---
title: Mise hors service de votre environnement Skype pour entreprises sur site
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instructions pour la mise hors service de votre environnement Skype Entreprise local.
ms.openlocfilehash: 46848c6730d37f549a8d5ee16f066fa67c789873
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656680"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Mise hors service de votre environnement Skype pour entreprises sur site

Si votre organisation utilise Teams ou Skype Entreprise Online avec un déploiement local de Skype Entreprise Server, vous pouvez migrer ces environnements entièrement vers le cloud, puis retirer votre déploiement local de Skype Entreprise Server. 

> [!NOTE]
> Avant de désaffecter votre environnement local, vous devez configurer la connectivité hybride entre votre déploiement local et Microsoft 365. [](configure-hybrid-connectivity.md) Après avoir configuré la connectivité hybride, vous pouvez migrer les utilisateurs vers le cloud, lors de la migration de leurs réunions en local et de la migration de tous les contacts de Skype Entreprise Server vers Teams. La configuration de la connectivité hybride est une étape requise pour migrer les utilisateurs de l’local vers le cloud et garantir l’ensemble des fonctionnalités de Teams.

Pour effectuer votre déplacement de l’environnement local vers le cloud et désaffecter votre environnement Skype Entreprise Server local, vous devez effectuer les étapes suivantes dans l’ordre suivant :

- **Étape 1.** [Déplacez tous les utilisateurs requis de l’local vers le site en ligne.](decommission-move-on-prem-users.md)

- **Étape 2.** [Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)

- **Étape 3.** [Déplacez les points de terminaison de l’application hybride de l’local vers le mode en ligne.](decommission-move-on-prem-endpoints.md)

- **Étape 4.** [Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)
