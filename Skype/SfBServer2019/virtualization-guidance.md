---
title: 'Prise en charge de la virtualisation Skype Entreprise Server 2019 '
ms.reviewer: corbinm
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Résumé : Découvrez la prise en charge de la virtualisation pour Skype Entreprise Server 2019.'
ms.openlocfilehash: 850bfc0ae19aa8391baca6c9a8b6f1dde85cde2d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767102"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Prise en charge de la virtualisation Skype Entreprise Server 2019

Skype Entreprise Server 2019 est pris en charge sur la virtualisation.

Bien que la virtualisation soit prise en charge, il existe quelques points clés à retenir :

- Maintenez un rapport 1:1 entre l’UC virtuelle et l’UC physique.
- Ne déplacez pas un serveur invité pendant son fonctionnement.
- La migration d’un système en direct et la portabilité d’une machine virtuelle ne sont pas pris en charge.
- Désactivez l’hyper-threading sur tous les hôtes.
- Ne configurez pas la mémoire dynamique sur les serveurs hôtes.
- Utilisez des disques fixes ou pass-through plutôt que des disques dynamiques.
- Autorisez une surcharge de 6 à 10 % pour les hyperviseurs au-delà de ce dont l’invité virtuel a besoin.

## <a name="supported-hypervisors"></a>Hyperviseurs pris en charge

SfB Server 2019 est pris en charge sur Windows Server 2016 et Windows Server 2019.

Pour les hyperviseurs tiers, vous avez besoin d’un hyperviseur qui a réussi le test SVVP (Server Virtualization Validation Program) pour le système d’exploitation approprié.

- Consultez les [Windows Server 2016 dans](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) la liste SVVP.
- Voir les [Windows Server 2019 dans](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) la liste SVVP.

## <a name="stress-and-performance-tool"></a>Outil Stress and performance

L Skype Entreprise Server 2019 Stress and Performance Tool inclut des outils qui simplifient la planification de la capacité Skype Entreprise Server 2019. L Skype Entreprise Server 2019 Stress and Performance Tool vous aidera à :

- Simplifier la planification matérielle pour Skype Entreprise Server 2019
- Vous fournir des connaissances accrues et des meilleures pratiques pour l’optimisation des performances
- Mesurer les performances de vos déploiements Skype Entreprise Server 2019
 
Vous pouvez télécharger l’outil à partir [d’ici.](https://www.microsoft.com/download/details.aspx?id=101447)
