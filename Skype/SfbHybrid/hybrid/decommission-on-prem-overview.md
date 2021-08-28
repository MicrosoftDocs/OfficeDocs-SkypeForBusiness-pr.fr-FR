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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instructions pour la mise hors service de votre environnement Skype Entreprise local.
ms.openlocfilehash: 53ed840c89ab02eff87607f0bdffebcef94fd4e2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583388"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Mise hors service de votre environnement Skype pour entreprises sur site

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Si votre organisation utilise Teams avec un déploiement local de Skype Entreprise Server, vous pouvez migrer ces environnements entièrement vers le cloud, puis retirer votre déploiement local de Skype Entreprise Server. 

> [!NOTE]
> Avant de désaffecter votre environnement local, vous devez configurer la connectivité hybride entre votre déploiement local et Microsoft 365. [](configure-hybrid-connectivity.md) Après avoir configuré la connectivité hybride, vous pouvez migrer les utilisateurs vers le cloud, lors de la migration de leurs réunions en local et de la migration de tous les contacts de Skype Entreprise Server vers Teams. La configuration de la connectivité hybride est une étape requise pour migrer les utilisateurs de l’local vers le cloud et pour garantir l’Teams complète.

Pour effectuer votre déplacement de l’environnement local vers le cloud et désaffecter votre environnement Skype Entreprise Server local, vous devez effectuer les étapes suivantes dans l’ordre suivant :

- **Étape 1.** [Déplacez tous les utilisateurs requis de l’local vers le site en ligne.](decommission-move-on-prem-users.md)

- **Étape 2.** [Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)

- **Étape 3.** [Déplacez les points de terminaison de l’application hybride de l’local vers le mode en ligne.](decommission-move-on-prem-endpoints.md)

- **Étape 4.** [Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)

