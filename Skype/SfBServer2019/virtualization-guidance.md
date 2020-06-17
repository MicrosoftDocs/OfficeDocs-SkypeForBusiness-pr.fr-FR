---
title: 'Prise en charge de la virtualisation pour Skype entreprise Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Découvrez la prise en charge de la virtualisation pour Skype entreprise Server 2019.'
ms.openlocfilehash: b4524b1284a85e7ab372b415d45c2005f8212887
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755808"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Prise en charge de la virtualisation pour Skype entreprise Server 2019

Skype entreprise Server 2019 est pris en charge sur la virtualisation.

Bien que la virtualisation soit prise en charge, il existe certains points clés à garder à l’esprit :

- Conservez un ratio de 1:1 d’UC virtuelle/unité centrale physique.
- Ne pas déplacer un serveur invité pendant qu’il fonctionne.
- La migration d’un système actif et la portabilité d’une machine virtuelle ne sont pas prises en charge.
- Désactivez la technologie Hyper-Threading sur tous les hôtes.
- Ne configurez pas de mémoire dynamique sur les serveurs hôtes.
- Utilisez des disques fixes ou passés plutôt que des disques dynamiques.
- Autoriser une charge de travail de 6-10 pour cent pour les hyperviseurs au-delà de ce que requiert l’invité virtuel.

## <a name="supported-hypervisors"></a>Hyperviseurs pris en charge

SfB Server 2019 est pris en charge sur Windows Server 2016 et Windows Server 2019.

Pour les hyperviseurs tiers, vous avez besoin d’un hyperviseur qui a réussi le test du programme de validation de la virtualisation de serveur (SVVP) pour le système d’exploitation concerné.

- Voir les [versions de Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) dans la liste SVVP.
- Voir les [versions de Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) dans la liste SVVP.

## <a name="stress-and-performance-tool"></a>Outil stress and performance

L’outil stress and performance de Skype entreprise Server 2019 inclut des outils qui simplifient la planification de la capacité pour Skype entreprise Server 2019. L’outil stress and performance de Skype entreprise Server 2019 vous permet d’effectuer les opérations suivantes :

- Simplifier la planification de votre matériel pour Skype entreprise Server 2019
- Vous fournir des connaissances et meilleures pratiques accrues pour le réglage des performances
- Mesurer les performances de vos déploiements Skype entreprise Server 2019 envisagés
 
Vous pouvez télécharger l’outil à partir de [cet emplacement](https://www.microsoft.com/download/details.aspx?id=101447).
