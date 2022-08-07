---
title: Gérer les Mises à jour Windows pour Salles Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: ''
description: Administration pouvez en savoir plus sur la gestion des mises à jour des fonctionnalités Windows Mises à jour et Windows pour Salles Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1df5521bdfafe38854a0b6a3821e86218ce95a0b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272179"
---
# <a name="manage-windows-updates"></a>Gérer les Mises à jour Windows

Salles Microsoft Teams s’exécute sur Windows 10 Entreprise IoT ou Windows 10 Entreprise (VL) et reçoit les mêmes builds windows Mises à jour et de système d’exploitation qu’un ordinateur de bureau standard.

Windows Mises à jour peut être géré comme indiqué dans les sections suivantes :

## <a name="hands-off-approach"></a>Approche pratique 

- Par défaut, les mises à jour sont téléchargées directement à partir de Windows Mises à jour automatiquement et installées pendant les heures creuses.
- Les Mises à jour non reportables installent automatiquement le premier jour de la mise en production.
- Les Mises à jour de qualité et les pilotes téléchargent et installent automatiquement le premier jour.
- Mises à jour de fonctionnalités. Consultez les notes qui suivent.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Mises à jour for Business (GPO ou Intune)  

- [Téléchargement de Windows Mises à jour for Business](/windows/deployment/update/waas-manage-updates-wufb)
- Mises à jour sont téléchargées à partir de Windows Update ou de votre Windows Server Update Services (WSUS), mais avec des retards configurés après la date de publication d’origine.
- Vous pouvez utiliser plusieurs unités d’organisation ou stratégies filtrées pour créer des « anneaux » de déploiement où les administrateurs peuvent spécifier les salles Teams appareils qui installent la qualité Mises à jour en premier et celles qui sont installées ultérieurement. La fiabilité et les performances peuvent être testées sur un sous-ensemble d’appareils avant de déployer des mises à jour sur l’ensemble du déploiement sans la surcharge liée à la gestion des Mises à jour Windows dans Configuration Manager.
- WSUS et Windows Mises à jour for Business peuvent être [configurés en même temps](/windows/deployment/update/waas-integrate-wufb) si vous souhaitez la gestion de la bande passante et le contrôle fourni par Windows Mises à jour for Business.
- Mises à jour des fonctionnalités. Consultez les notes qui suivent.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Téléchargement WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Tout comme Windows Update entreprise, mais avec l’option supplémentaire de cibler des bases de connaissances spécifiques dans chaque « anneau » ou dans l’ensemble du déploiement. Chaque mise à jour peut être déployée et testée individuellement à volonté, au lieu de s’appuyer uniquement sur un délai.
- Mises à jour des fonctionnalités. Consultez les notes qui suivent.

### <a name="feature-updates"></a>Mises à jour des fonctionnalités

Contrairement aux mises à jour qualité et non différées, Windows 10 « Feature Mises à jour » (versions majeures du système d’exploitation) ne sera installé qu’après les tests de Microsoft et valide une fonctionnalité de mise à jour donnée avec Salles Microsoft Teams. Même si la mise à jour est publiée sur le canal Semi-Annual (ou ciblée si vous avez des systèmes définis sur ce canal pour les tests) ou envoyée manuellement, Salles Microsoft Teams n’autorise pas l’installation de la mise à jour non testée.

Salles Microsoft Teams fonctions « out-of-box » avec une approche pratique. salles Teams télécharger une mise à jour et attendre le prochain redémarrage pour l’installer. Sauf si quelqu’un le redémarre manuellement, l’installation se produit uniquement au redémarrage automatique tous les soirs. Windows Mises à jour doit être transparent dans la pièce, et le fonctionnement normal ne doit jamais être interrompu par Windows Mises à jour.

Si vous choisissez de joindre des appareils à un domaine, vous pouvez utiliser Microsoft Endpoint Configuration Manager ou WSUS. Portez une attention particulière aux stratégies ou actions qui entraînent une mise à jour de l’appareil ou un redémarrage forcé pendant les heures d’ouverture. salles Teams ne doit pas redémarrer pendant l’utilisation ni alerter sur Windows Mises à jour sur l’interface utilisateur pendant les heures d’utilisation. Examinez votre configuration si ce comportement se produit.
