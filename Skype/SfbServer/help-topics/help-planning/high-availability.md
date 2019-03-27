---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Le jeu de haute disponibilité principal pour la plupart des rôles de serveur dans Skype pour Business Server 2015 est basé sur la redondance des serveurs via un regroupement. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
ms.openlocfilehash: 50cc5f371e4964555aae2a7f50ce3d1431f4f10c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874024"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
Le jeu de haute disponibilité principal pour la plupart des rôles de serveur dans Skype pour Business Server 2015 est basé sur la redondance des serveurs via un regroupement. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
  
Skype pour Business Server 2015 nécessite au moins deux serveurs frontaux afin d’activer la haute disponibilité. L’outil de planification utilise les critères suivants pour déterminer si elle ajoute des serveurs supplémentaires afin de prendre en charge la haute disponibilité :
  
- Si le déploiement contient deux ou plusieurs serveurs frontaux, l’outil de planification n’ajoute pas un serveur supplémentaire.
    
- Si le déploiement contient un serveur Edge, un serveur supplémentaire est ajouté. 
    
- Si le déploiement contient la conversation permanente, l’outil de planification ajouter un serveur supplémentaire, mais pas augmenter le nombre de pool. Par exemple, si le déploiement déjà contient quatre serveurs, l’outil de planification suggère Ajout d’un serveur supplémentaire (pour un total de cinq serveurs) mais conserve un seul pool. 
    
L’outil de planification ajoute également une base de données miroir SQL pour toutes les bases de données. Par exemple, s’il existe une base de données du serveur frontal SQL, l’outil de planification seront ajoutez la base de données en tant que la base de données miroir pour celle-ci et nommez-le comme « Front-End miroir SQL base de données.
  
Pour plus d’informations sur la préparation de votre environnement pour une haute disponibilité, voir [planifier la haute disponibilité et de récupération d’urgence dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

