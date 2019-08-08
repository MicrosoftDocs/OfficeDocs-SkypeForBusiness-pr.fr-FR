---
title: Gestion des mises à jour Windows pour les salles de Microsoft teams
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Gestion des mises à jour Windows pour les salles de Microsoft teams
ms.openlocfilehash: 434e6d28796662c1cc8904b7ad94f059d7d447b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243277"
---
# <a name="manage-windows-updates"></a>Gérer les mises à jour Windows

Microsoft teams Room s’exécute sur Windows 10 entreprise IoT ou Windows 10 entreprise (VL) et reçoit les mêmes mises à jour Windows et les mêmes versions de système d’exploitation que le bureau standard.

Les mises à jour de Windows peuvent être gérées de différentes manières:

## <a name="hands-off-approach"></a>Approche mains libres 

- Les mises à jour peuvent être téléchargées directement à partir des mises à jour Windows et installées pendant les heures creuses. Il s’agit de la configuration par défaut.
- Mises à jour non différées installation de Day-One de version automatique.
- Les mises à jour et les mises à jour de qualité sont téléchargées et installées automatiquement.
- Mises à jour de fonctionnalités. Voir les notes suivantes.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Mises à jour Windows pour les entreprises (GPO ou Intune)  

- [Mises à jour Windows pour](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) le téléchargement d’une entreprise
- Les mises à jour sont téléchargées à partir de la version WU ou de votre WSUS, mais avec les retards configurés au-delà de la date de publication initiale du KB
- Utilisé avec les stratégies de plusieurs UO ou filtrées, vous pouvez créer des «anneaux» de déploiement dans lesquels les administrateurs peuvent spécifier les appareils qui installent les mises à jour de qualité et celles qui sont installées plus tard. Cela permet des tests de fiabilité et de performance sur un sous-ensemble de systèmes avant de déployer des mises à jour au sein de l’ensemble du déploiement, sans la surcharge de la gestion des mises à jour Windows dans SCCM par exemple.
- Les mises à jour de WSUS et Windows pour l’entreprise peuvent être [configurées en même temps](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) si vous souhaitez disposer de la gestion de la bande passante et du contrôle des mises à jour de Windows pour les entreprises.
- Mises à jour de fonctionnalités. Voir les notes suivantes.

## <a name="wsussccm"></a>WSUS/SCCM

- Téléchargement de [WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Comme Windows Update pour les entreprises, mais avec l’option supplémentaire de ciblage des Ko spécifiques dans chaque «anneau» ou le déploiement complet. Chaque mise à jour peut être déployée et testée individuellement à la place, plutôt que d’utiliser un délai unique.
- Mises à jour de fonctionnalités. Voir les notes suivantes.

### <a name="feature-updates"></a>Mises à jour de fonctionnalités

Contrairement aux mises à jour de qualité et non différées, les mises à jour de fonctionnalité de Windows 10 "(versions majeures du système d’exploitation) ne sont installées qu’après que Microsoft teste et valide une fonctionnalité mises à jour données à l’aide des salles de Microsoft Teams. Même si la mise à jour est publiée sur le canal semi-annuel (ou ciblée si des systèmes sont définis sur ce canal à des fins de test), ou si vous avez effectué une mise à jour manuelle, un appareil de systèmes de salle Microsoft n’autorise pas l’installation de la mise à jour non testée.

Dans le cadre de la mise à jour de Microsoft Teams, la mise à jour de Windows et le redémarrage automatique d’un appareil pour une mise à jour Windows. Les systèmes risquent de télécharger une mise à jour et d’attendre le prochain redémarrage pour l’installer. Si une personne ne le redémarre manuellement, l’installation doit se produire lors du redémarrage automatique. Les mises à jour Windows doivent être transparentes dans la salle, de sorte que l’interface utilisateur ne doit jamais être interrompue par des mises à jour Windows.

Si vous choisissez d’utiliser les appareils joints au domaine, utilisez SCCM ou WSUS. Soyez particulièrement attentif aux politiques et aux actions susceptibles d’entraîner l’installation d’une mise à jour ou à un redémarrage forcé pendant les heures d’activité. Les systèmes de votre déploiement ne doivent pas redémarrer lors de l’utilisation d’une alerte ou d’une alerte sur les mises à jour Windows sur l’interface utilisateur pendant les heures d’utilisation; examinez votre configuration si ce comportement se produit.