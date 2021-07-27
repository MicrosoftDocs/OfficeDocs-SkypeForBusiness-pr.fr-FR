---
title: Déplacer des utilisateurs vers le cloud
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
description: Déplacez les utilisateurs avant de désaffecter Skype Entreprise environnement local.
ms.openlocfilehash: bc98ebfcfb7ad4d4b2c64942b5f84500a98cdc84
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510715"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>Déplacer les utilisateurs requis avant de désaffecter votre environnement local

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cet article explique comment déplacer les utilisateurs requis vers le cloud Microsoft avant de désaffecter votre environnement Skype Entreprise local. Il s’agit de l’étape 1 des étapes suivantes pour désaffecter votre environnement local :

- **Étape 1. Déplacez tous les utilisateurs requis de l’local vers le site en ligne.** (Cet article)

- Étape 2. [Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)

- Étape 3. [Migrez les points de terminaison de l’application hybride de l’local vers le mode en ligne.](decommission-move-on-prem-endpoints.md) N’ignorez pas que les points de terminaison d’applications hybrides existants ne seront pas découvrables entre le moment où vous effectuez l’étape 2 ci-dessus, jusqu’à ce que vous complétiez cette étape. Vous devez planifier les deux étapes 2 et 3 dans la même fenêtre de maintenance.

- Étape 4. [Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Déplacer tous les utilisateurs requis de l’local vers le cloud

Tous les utilisateurs que vous continuerez à utiliser après avoir effectué la migration doivent d’abord être déplacés de l’local vers le cloud. Vous déplacez les utilisateurs à l’aide des outils d’administration locaux. Pour plus d’informations, voir [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).

Bien qu’il soit possible pour les utilisateurs ayant des comptes Skype Entreprise Server locaux d’utiliser Teams, ces utilisateurs ne peuvent pas utiliser toutes les fonctionnalités de Teams. Ces utilisateurs ne peuvent pas interopérer ou fédérer avec d’autres utilisateurs qui utilisent encore Skype Entreprise (en ligne ou en local). Ces utilisateurs ne peuvent pas non plus recevoir d’appels PSTN dans leur client Teams client. Par conséquent, vous devez déplacer ces utilisateurs en ligne. Cette étape garantit également que tous les contacts ou réunions créés dans Skype Entreprise Server sont migrés vers Teams.

Pour vérifier s’il reste des utilisateurs dans votre déploiement local, exécutez l’cmdlet suivante dans Skype Entreprise Server fenêtre PowerShell.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Si des utilisateurs sont renvoyés, examinez la sortie pour déterminer si des comptes doivent être déplacés vers le cloud et, pour ces utilisateurs, suivez les étapes [ci-après.](move-users-between-on-premises-and-cloud.md) Pour les comptes d’utilisateurs qui ne sont plus nécessaires, exécutez l’Skype Entreprise Server cmdlet PowerShell suivante :

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> L'Disable-CsUser supprimera tous les attributs Skype Entreprise de tous les utilisateurs qui ont les critères de filtre. Avant de continuer, confirmez que ces comptes ne sont plus nécessaires à l’avenir.


Vous êtes maintenant prêt à [désactiver votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>Voir aussi

- [Mise hors service de votre environnement Skype pour entreprises sur site](decommission-on-prem-overview.md)

- [Désactiver votre configuration hybride](cloud-consolidation-disabling-hybrid.md)

- [Déplacer des points de terminaison d’application hybride de l’local vers le mode en ligne](decommission-move-on-prem-endpoints.md)

- [Supprimez votre déploiement sur site de Skype pour entreprises.](decommission-remove-on-prem.md)




