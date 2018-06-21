---
title: Haute disponibilité (outil de planification)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Le jeu de haute disponibilité principal pour la plupart des rôles de serveur dans Skype pour Business Server repose sur la redondance des serveurs via un regroupement. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
ms.openlocfilehash: 9948fbc4f1daff73afa020b83357a26c185d7785
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19977263"
---
# <a name="high-availability-planning-tool"></a>Haute disponibilité (outil de planification)
 
Le jeu de haute disponibilité principal pour la plupart des rôles de serveur dans Skype pour Business Server repose sur la redondance des serveurs via un regroupement. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
  
Skype pour Business Server nécessite au moins deux serveurs frontaux afin d’activer la haute disponibilité. L’outil de planification utilise les critères suivants pour déterminer si elle ajoute des serveurs supplémentaires afin de prendre en charge la haute disponibilité :
  
- Si le déploiement contient deux ou plusieurs serveurs frontaux, l’outil de planification n’ajoute pas un serveur supplémentaire.
    
- Si le déploiement contient un serveur Edge, un serveur supplémentaire est ajouté. 
    
- Si le déploiement contient la conversation permanente, l’outil de planification ajouter un serveur supplémentaire, mais pas augmenter le nombre de pool. Par exemple, si le déploiement déjà contient quatre serveurs, l’outil de planification suggère Ajout d’un serveur supplémentaire (pour un total de cinq serveurs) mais conserve un seul pool. 
    
L’outil de planification ajoute également une base de données miroir SQL pour toutes les bases de données. Par exemple, s’il existe une base de données du serveur frontal SQL, l’outil de planification seront ajoutez la base de données en tant que la base de données miroir pour celle-ci et nommez-le comme « Front-End miroir SQL base de données.
  
Pour plus d’informations sur la préparation de votre environnement pour une haute disponibilité, voir [planifier la haute disponibilité et de récupération d’urgence dans Skype pour Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

