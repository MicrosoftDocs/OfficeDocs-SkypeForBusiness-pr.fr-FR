---
title: Gérer les mises à jour Windows pour les salles Microsoft Teams
ms.author: v-cichur
author: cichur
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
description: Gérer les mises à jour Windows pour les salles Microsoft Teams
ms.openlocfilehash: cb3007acd31f84cedb8996f440b9634f0551f638
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103200"
---
# <a name="manage-windows-updates"></a>Gérer les mises à jour Windows

Salles Microsoft Teams s’exécute sur Windows 10 Entreprise IoT ou Windows 10 Entreprise (VL) et reçoit les mêmes mises à jour Windows et builds de système d’exploitation qu’un bureau standard.

Les mises à jour Windows peuvent être gérées de différentes manières :

## <a name="hands-off-approach"></a>Approche pratique 
- Les mises à jour peuvent être téléchargées directement à partir des mises à jour Windows automatiquement et installées pendant les heures d’ouverture. Si aucune modification n’est faite à la configuration, il s’agit de l’état par défaut.
- Les mises à jour non reportables installent automatiquement le premier jour de la publication. 
- Les mises à jour qualité et les pilotes téléchargent et installent automatiquement le premier jour. 
- Mises à jour de fonctionnalités. Voir les remarques supplémentaires ci-dessous. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) (GPO ou Intune)   
- Les mises à jour sont téléchargées à partir de WU ou de votre WSUS, mais avec des retards configurés au-delà de la date de publication d’origine de la ko. 
- Combiné à plusieurs stratégies d’une ou de plusieurs ou filtrées, cela permet de créer des « anneaux » de déploiement, où les administrateurs peuvent spécifier les appareils qui installent les mises à jour qualité en premier et ceux qui seront installés ultérieurement. Cela permet de tester la fiabilité et les performances sur un sous-ensemble de systèmes avant de déployer les mises à jour dans l’ensemble du déploiement sans la surcharge de gestion des mises à jour Windows dans Microsoft Endpoint Configuration Manager, par exemple.
- WSUS et Windows Updates [](/windows/deployment/update/waas-integrate-wufb) for Business peuvent être configurés en même temps si vous souhaitez à la fois gérer la bande passante et contrôler les mises à jour Windows pour Entreprise.
- Mises à jour de fonctionnalités. Voir les remarques supplémentaires ci-dessous.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Tout comme Windows Update for Business, mais avec l’option supplémentaire de ciblage de ko spécifiques au sein de chaque « anneau » ou de l’ensemble du déploiement. Chaque mise à jour peut être déployée et testée individuellement à votre volonté, au lieu de compter uniquement sur un délai. 
- Mises à jour de fonctionnalités. Voir les remarques supplémentaires ci-dessous.


### <a name="feature-updates"></a>Mises à jour de fonctionnalités

Contrairement aux mises à jour qualité et non reportables, les « mises à jour de fonctionnalités » Windows 10 (principales mises à jour du système d’exploitation) ne sont installées qu’après que Microsoft a effectué des tests et validé une fonctionnalité de mise à jour donnée avec les salles Microsoft Teams. Même s’il est publié sur le canal Semi-Annual (ou ciblé si vous avez des systèmes définies sur ce canal pour les tests) ou même manuellement poussée par vos propres tentatives ou configurations, il n’autorise pas l’installation tant que le bloc de notre part n’est pas supprimé.

La salle Microsoft Teams « out-of-box », à l’aide de l’approche pratique, n’installera pas windows Update ou ne redémarrera pas automatiquement un appareil en raison d’une mise à jour Windows. Toutefois, les systèmes peuvent télécharger une mise à jour et attendre le redémarrage suivant pour l’installer. Sauf si quelqu’un le redémarre manuellement, l’installation doit avoir lieu au redémarrage automatique de la nuit. Les mises à jour Windows doivent être transparentes dans la salle, l’interface utilisateur ne doit jamais être interrompue par les mises à jour Windows.

Si vous choisissez de joindre un domaine, utilisez Microsoft Endpoint Configuration Manager ou WSUS, et veuillez prêter une attention particulière aux stratégies ou actions qui peuvent entraîner l’installation d’une mise à jour ou le forçage d’un redémarrage pendant les heures d’ouverture. Si vous avez des systèmes dans votre redémarrage de déploiement lors de l’utilisation ou des alertes sur les mises à jour Windows sur l’interface utilisateur, vous pouvez examiner votre configuration.