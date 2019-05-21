---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Le schéma principal de haute disponibilité pour la plupart des rôles serveur dans Skype entreprise Server est basé sur la redondance du serveur via le regroupement. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
ms.openlocfilehash: 2a3327bcf5b17df7bc6eb4880a9966764786560d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281587"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
Le schéma principal de haute disponibilité pour la plupart des rôles serveur dans Skype entreprise Server est basé sur la redondance du serveur via le regroupement. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
  
Skype entreprise Server nécessite au moins deux serveurs front-end pour garantir une haute disponibilité. L’outil de planification utilise les critères suivants pour déterminer s’il ajoute des serveurs supplémentaires afin de prendre en charge une haute disponibilité:
  
- Si le déploiement comporte au moins deux serveurs front-end, l’outil de planification n’ajoute pas de serveur supplémentaire.
    
- Si le déploiement contient un serveur Edge, un serveur supplémentaire est ajouté. 
    
- Si le déploiement contient une conversation permanente, l’outil de planification ajoutera un serveur supplémentaire, mais n’augmentera pas le numéro de la liste. Par exemple, si le déploiement comporte déjà quatre serveurs, l’outil de planification suggère l’ajout d’un serveur supplémentaire (pour un total de 5 serveurs), mais conserve un pool unique. 

    > [!NOTE] 
    > La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique [mise à niveau de Skype entreprise vers Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams). Si vous avez besoin d’utiliser une conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 

    
L’outil de planification ajoute également une base de données SQL miroir pour toutes les bases de données. Par exemple, si vous disposez d’une base de données SQL Server frontale, l’outil de planification ajoutera l’autre base de données en tant que base de données miroir pour celle-ci et la nommera en tant que base de données SQL miroir frontale.
  
Pour plus d’informations sur la préparation de votre environnement en vue d’une haute disponibilité, voir [prévoir une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

