---
title: Gestion des mises à jour Windows pour les salles de Microsoft teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Gestion des mises à jour Windows pour les salles de Microsoft teams
ms.openlocfilehash: 9b195b4158f234146c362b65642d53960c9f5c24
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817195"
---
# <a name="manage-windows-updates"></a>Gérer les mises à jour Windows

Microsoft teams Room s’exécute sur Windows 10 entreprise IoT ou Windows 10 entreprise (VL) et reçoit les mêmes mises à jour Windows et les mêmes versions de système d’exploitation que le bureau standard.

Les mises à jour de Windows peuvent être gérées de différentes manières :

## <a name="hands-off-approach"></a>Approche mains libres 
- Les mises à jour peuvent être téléchargées directement à partir des mises à jour Windows et installées pendant les heures creuses. Si aucune modification n’est apportée à la configuration, il s’agit de l’État par défaut.
- Les mises à jour non différées sont installées en une seule version. 
- Les mises à jour et pilotes de qualité sont téléchargés et installés automatiquement. 
- Mises à jour de fonctionnalités. Voir les remarques supplémentaires ci-dessous. 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[Mises à jour Windows pour les entreprises](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO ou Intune)   
- Les mises à jour sont téléchargées à partir de la version WU ou de votre WSUS, mais avec les retards configurés au-delà de la date de publication initiale du KB 
- Combinée à plusieurs stratégies de l’unité d’organisation ou filtrées, cela permet de créer des « anneaux » de déploiement, permettant aux administrateurs de spécifier les appareils qui installent les mises à jour de qualité et celles qui doivent être installées par la suite. Cela permet d’effectuer des tests de fiabilité et de performance sur un sous-ensemble de systèmes avant de déployer des mises à jour au sein de tout le déploiement sans la surcharge de la gestion des mises à jour Windows dans le gestionnaire de configuration de points de terminaison Microsoft, par exemple.
- Les mises à jour de WSUS et Windows pour l’entreprise peuvent être [configurées en même temps](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) si vous souhaitez une gestion de la bande passante et le contrôle des mises à jour de Windows pour les entreprises.
- Mises à jour de fonctionnalités. Voir les remarques supplémentaires ci-dessous.

## <a name="wsusconfiguration-managerhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Comme Windows Update pour les entreprises, mais avec l’option supplémentaire de ciblage des Ko spécifiques dans chaque « anneau » ou le déploiement complet. Chaque mise à jour peut être déployée et testée individuellement à la place, plutôt que d’utiliser un délai unique. 
- Mises à jour de fonctionnalités. Voir les remarques supplémentaires ci-dessous.


### <a name="feature-updates"></a>Mises à jour de fonctionnalités

Contrairement aux mises à jour de qualité et non différées, les mises à jour de fonctionnalité de Windows 10 "(versions majeures du système d’exploitation) ne sont installées qu’après que Microsoft teste et valide une fonctionnalité mises à jour données dans les salles de Microsoft Teams. Même si celle-ci est publiée sur le canal semi-annuel (ou ciblée si vous disposez de systèmes pour le test), ou si elle est activée manuellement par vos propres tentatives ou configurations, l’installation ne sera pas autorisée tant que le blocage de la fin n’aura pas été supprimé.

Salle Microsoft teams « out-of-Box », en utilisant l’approche mains libres, n’installe pas Windows Update ou ne redémarre pas automatiquement un appareil suite à une mise à jour Windows. Néanmoins, il est possible que les systèmes téléchargent une mise à jour et attendent le prochain redémarrage pour l’installer. Si une personne ne le redémarre manuellement, l’installation doit se produire lors du redémarrage automatique. Les mises à jour Windows doivent être transparentes dans la salle, de sorte que l’interface utilisateur ne doit jamais être interrompue par des mises à jour Windows.

Si vous choisissez l’accès au domaine, utilisez le gestionnaire de configuration de point de terminaison Microsoft ou les services WSUS, et soyez particulièrement attentif aux stratégies ou aux actions susceptibles d’entraîner l’installation d’une mise à jour ou de l’exécution forcée d’un redémarrage pendant les heures d’activité. Si votre déploiement a des systèmes en redémarrant lors de l’utilisation ou d’une alerte sur les mises à jour Windows sur l’interface utilisateur, vous pouvez effectuer des recherches dans votre configuration.
