---
title: Gestion des mises à jour Windows pour les salles de Microsoft teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Gestion des mises à jour Windows pour les salles de Microsoft teams
ms.openlocfilehash: be3555507b0c9a8967b444b96e8c6e4af8f35fbf
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628560"
---
# <a name="manage-windows-updates"></a>Gérer les mises à jour Windows

Microsoft teams Room s’exécute sur Windows 10 entreprise IoT ou Windows 10 entreprise (VL) et reçoit les mêmes mises à jour Windows et les mêmes versions de système d’exploitation que l’ordinateur de bureau standard.

Les mises à jour de Windows peuvent être gérées comme décrit dans les sections suivantes :

## <a name="hands-off-approach"></a>Approche mains libres 

- Par défaut, les mises à jour sont téléchargées directement à partir des mises à jour de Windows automatiquement et sont installées pendant les heures creuses.
- Mises à jour non différées installation de Day-One de version automatique.
- Les mises à jour et les mises à jour de qualité sont téléchargées et installées automatiquement.
- Mises à jour de fonctionnalités. Voir les notes suivantes.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Mises à jour Windows pour les entreprises (GPO ou Intune)  

- [Mises à jour Windows pour](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) le téléchargement d’une entreprise
- Les mises à jour sont téléchargées à partir de Windows Update ou de votre WSUS, mais avec des retards configurés au-delà de la date de publication initiale.
- Vous pouvez utiliser plusieurs UO ou des stratégies filtrées pour créer des « anneaux » de déploiement, où les administrateurs peuvent spécifier les appareils qui installent les mises à jour de qualité et celles qui s’y trouvent. La fiabilité et les performances peuvent être testées sur un sous-ensemble de systèmes avant de déployer des mises à jour au sein de l’ensemble du déploiement, sans la surcharge de la gestion des mises à jour Windows dans Configuration Manager.
- Les mises à jour de WSUS et Windows pour l’entreprise peuvent être [configurées en même temps](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) si vous souhaitez disposer de la gestion de la bande passante et du contrôle des mises à jour de Windows pour les entreprises.
- Mises à jour de fonctionnalités. Voir les notes suivantes.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- Téléchargement de [WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Comme Windows Update pour les entreprises, mais avec l’option supplémentaire de ciblage des Ko spécifiques dans chaque « anneau » ou le déploiement complet. Chaque mise à jour peut être déployée et testée individuellement à la place, plutôt que d’utiliser un délai unique.
- Mises à jour de fonctionnalités. Voir les notes suivantes.

### <a name="feature-updates"></a>Mises à jour de fonctionnalités

Contrairement aux mises à jour de qualité et non différées, les mises à jour de fonctionnalité de Windows 10 "(versions majeures du système d’exploitation) ne sont installées qu’après que Microsoft teste et valide une fonctionnalité mises à jour données à l’aide des salles de Microsoft Teams. Même si la mise à jour est publiée sur le canal semi-annuel (ou ciblée si des systèmes sont définis sur ce canal à des fins de test), ou si vous avez effectué une mise à jour manuelle, un appareil de systèmes de salle Microsoft n’autorise pas l’installation de la mise à jour non testée.

Les fonctions salles de Microsoft Teams, « prédéfinis », qui ne permettent pas l’installation d’une mise à jour Windows ou le redémarrage automatique d’un appareil pour une mise à jour Windows. Les systèmes téléchargent une mise à jour et attendent le prochain redémarrage pour l’installer. À moins qu’une personne ne la redémarre manuellement, l’installation ne se produit qu’après un redémarrage automatique. Les mises à jour Windows doivent être transparentes dans la salle, et l’opération normale ne doit jamais être interrompue par des mises à jour Windows.

Si vous choisissez de joindre des domaines, utilisez le gestionnaire de configuration de point de terminaison Microsoft ou WSUS. Soyez particulièrement attentif aux politiques ou aux actions qui engendrent une mise à jour de l’appareil ou un redémarrage forcé pendant les heures d’activité. Les systèmes de votre déploiement ne doivent pas redémarrer lors de l’utilisation d’une alerte ou d’une alerte sur les mises à jour Windows sur l’interface utilisateur pendant les heures d’utilisation ; examinez votre configuration si ce comportement se produit.