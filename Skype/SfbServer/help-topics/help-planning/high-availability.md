---
title: Skype Entreprise Server Outil de planification de la haute disponibilité
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Le principal schéma de haute disponibilité pour la plupart des rôles serveur dans Skype Entreprise Server 2015 est basé sur la redondance des serveurs via la mise en pool. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
ms.openlocfilehash: d8c6a16ba29d5725a148810c71a17325bdbab763
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234699"
---
# <a name="skype-for-business-server-high-availability-planning-tool"></a>Skype Entreprise Server Outil de planification de la haute disponibilité
 
Le principal schéma de haute disponibilité pour la plupart des rôles serveur dans Skype Entreprise Server 2015 est basé sur la redondance des serveurs via la mise en pool. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
  
Skype Entreprise Server 2015 nécessite au moins deux serveurs frontux pour activer la haute disponibilité. L’outil de planification utilise les critères suivants pour déterminer s’il ajoutera des serveurs supplémentaires pour prendre en charge la haute disponibilité :
  
- Si le déploiement contient au moins deux serveurs frontux, l’outil de planification n’ajoute pas de serveur supplémentaire.
    
- Si le déploiement contient un serveur Edge, un autre serveur est ajouté. 
    
- Si le déploiement contient une conversation permanente, l’outil de planification ajoute un serveur supplémentaire, mais n’augmente pas le nombre de pool. Par exemple, si le déploiement contient déjà quatre serveurs, l’outil de planification suggère l’ajout d’un autre serveur (pour un total de cinq serveurs), mais maintient un pool unique. 
    
L’outil de planification ajoute également une base de données SQL miroir pour toutes les bases de données. Par exemple, s’il existe une base de données SQL Server frontale, l’outil de planification ajoute l’autre base de données en tant que base de données miroir pour celle-ci et la nomme « base de données SQL frontale.
  
Pour plus d’informations sur la préparation de votre environnement pour la haute disponibilité, voir [Plan for high availability and disaster recovery in Skype Entreprise Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

