---
title: Haute disponibilité (outil de planification)
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
description: Le schéma principal de haute disponibilité pour la plupart des rôles de serveur dans Skype pour Business Server 2015 est basé sur la redondance des serveurs via un regroupement. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
ms.openlocfilehash: 8441db5ee4a84c573ed6a1642473b827382e4654
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="high-availability-planning-tool"></a>Haute disponibilité (outil de planification)
 
Le schéma principal de haute disponibilité pour la plupart des rôles de serveur dans Skype pour Business Server 2015 est basé sur la redondance des serveurs via un regroupement. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
  
Skype pour Business Server 2015 nécessite au moins deux serveurs frontaux afin de permettre une disponibilité élevée. L’outil de planification utilise les critères suivants pour déterminer si elle ajoute des serveurs supplémentaires pour prendre en charge la haute disponibilité :
  
- Si le déploiement contient deux ou plusieurs serveurs frontaux, l’outil de planification n’ajoute pas un serveur supplémentaire.
    
- Si le déploiement contient un serveur de transport Edge, un serveur supplémentaire est ajouté. 
    
- Si le déploiement contient Chat persistant, l’outil de planification ajouter un serveur supplémentaire, mais n’augmente pas le nombre de pool. Par exemple, si le déploiement déjà contient quatre serveurs, l’outil de planification suggère l’ajout d’un serveur (pour un total de cinq serveurs) mais conserve un pool unique. 
    
L’outil de planification ajoute également une base de données SQL de mise en miroir des bases de données. Par exemple, s’il existe une base de données de SQL Server avant fin, l’outil de planification s’ajouter la base de données comme la base de données mise en miroir de cette solution et nommez-le comme le « Front-End miroir SQL de base de données.
  
Pour plus d’informations sur la préparation de votre environnement pour une haute disponibilité, voir [planification de la haute disponibilité et reprise après sinistre dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

