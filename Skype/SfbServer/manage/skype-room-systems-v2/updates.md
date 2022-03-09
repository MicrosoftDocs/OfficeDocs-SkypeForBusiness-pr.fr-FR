---
title: Gérer Windows mises à jour de Salles Microsoft Teams
ms.author: serdars
author: SerdarSoysal
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: M365-voice
ms.assetid: ''
description: Gérer Windows mises à jour de Salles Microsoft Teams
ms.openlocfilehash: 1f5e297e699b4a6bc318f2ab7f2de6697cafada3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402878"
---
# <a name="manage-windows-updates"></a>Gérer Windows mises à jour

Salles Microsoft Teams s’exécute sur Windows 10 Entreprise IoT ou Windows 10 Entreprise (VL) et reçoit les mêmes mises à jour Windows de système d’exploitation qu’un bureau standard.

Windows mises à jour peuvent être gérées de différentes manières :

## <a name="hands-off-approach"></a>Approche pratique 
- Les mises à jour peuvent être téléchargées directement à partir Windows mises à jour automatiques et installées pendant les heures d’ouverture. Si aucune modification n’est faite à la configuration, il s’agit de l’état par défaut.
- Les mises à jour non reportables installent automatiquement le premier jour de la publication. 
- Les mises à jour qualité et les pilotes téléchargent et installent automatiquement le premier jour. 
- Mises à jour de fonctionnalités. Voir les remarques supplémentaires ci-dessous. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows mises à jour pour entreprise](/windows/deployment/update/waas-manage-updates-wufb) (GPO ou Intune)   
- Les mises à jour sont téléchargées à partir de WU ou de votre WSUS, mais avec des retards configurés au-delà de la date de publication d’origine de la ko. 
- Combiné à plusieurs stratégies d’une ou plusieurs ou filtrées, cela permet de créer des « anneaux » de déploiement, où les administrateurs peuvent spécifier quels appareils installent d’abord les mises à jour qualité et ceux qui seront installés ultérieurement. Cela permet de tester la fiabilité et les performances sur un sous-ensemble de systèmes avant de déployer des mises à jour dans l’ensemble du déploiement sans la surcharge de gestion des mises à jour Windows dans Microsoft Endpoint Configuration Manager par exemple.
- WSUS et Windows Updates for Business peuvent être configurés [](/windows/deployment/update/waas-integrate-wufb) en même temps si vous souhaitez gérer la bande passante et le contrôle Windows mises à jour pour les entreprises.
- Mises à jour de fonctionnalités. Voir les remarques supplémentaires ci-dessous.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Tout comme Windows Update for Business, mais avec l’option supplémentaire de ciblage de ko spécifiques au sein de chaque « anneau » ou de l’ensemble du déploiement. Chaque mise à jour peut être déployée et testée individuellement à votre volonté, au lieu de compter uniquement sur un délai. 
- Mises à jour de fonctionnalités. Voir les remarques supplémentaires ci-dessous.


### <a name="feature-updates"></a>Mises à jour de fonctionnalités

Contrairement aux mises à jour qualité et non reportables, Windows 10 « Mises à jour de fonctionnalités » (principales mises à jour du système d’exploitation) ne sera installée qu’après que Microsoft a effectué des tests et validé une fonctionnalité de mise à jour donnée avec Salles Microsoft Teams. Même s’il est publié sur le canal Semi-Annual (ou ciblé si vous avez des systèmes définies sur ce canal pour les tests) ou même manuellement poussée par vos propres tentatives ou configurations, il n’autorise pas l’installation tant que le bloc de notre part n’est pas supprimé.

Microsoft Teams salle « out-of-box », en utilisant l’approche mains libres, n’installe pas une mise à jour Windows ou ne redémarre pas automatiquement un appareil en raison d’une mise à jour Windows. Toutefois, les systèmes peuvent télécharger une mise à jour et attendre le redémarrage suivant pour l’installer. Sauf si quelqu’un le redémarre manuellement, l’installation doit avoir lieu au redémarrage automatique de la nuit. Windows mises à jour doivent être transparentes dans la salle, l’interface utilisateur ne doit jamais être interrompue Windows mises à jour.

Si vous choisissez de joindre un domaine, utilisez Microsoft Endpoint Configuration Manager ou WSUS, et veuillez prêter une attention particulière aux stratégies ou actions qui peuvent entraîner l’installation d’une mise à jour ou le forçage d’un redémarrage pendant les heures d’ouverture. Si vous avez des systèmes dans votre redémarrage de déploiement lors de l’utilisation ou des alertes sur les mises à jour Windows sur l’interface utilisateur, vous pouvez examiner votre configuration.