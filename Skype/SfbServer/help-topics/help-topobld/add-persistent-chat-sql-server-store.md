---
title: Ajouter un magasin SQL Server de conversation permanente
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Vous configurez les magasins SQL Server qui fourniront des bases de données pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.
ms.openlocfilehash: 856c74db37ef99243e024b0c044b20d095ca6ba6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899560"
---
# <a name="add-persistent-chat-sql-server-store"></a>Ajouter un magasin SQL Server de conversation permanente
 
Vous configurez les magasins SQL Server qui fourniront des bases de données pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.
  
 **Magasin SQL Server**: sélectionnez un serveur SQL Server existant et éventuellement une instance de conversation permanente.
  
Cliquez sur **Nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour les données de conversation permanente.
  
Activez la case à cocher **Activer magasin SQL Server de mise en miroir** pour configurer une base de données SQL Server et une instance facultative qui fournira une base de données en miroir pour les données de conversation permanente.
  
Sélectionnez dans la liste **magasin SQL Server de la mise en miroir** un serveur SQL Server et une instance facultative agir en tant que miroir SQL Server pour le serveur SQL de conversation permanente.
  
Cliquez sur **Nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour la mise en miroir du serveur SQL de la conversation permanente.
  
Sélectionnez la liste **utiliser SQL Server témoin pour activer le basculement automatique de mise en miroir** SQL Server qui jouera le rôle de serveur témoin dans les scénarios de basculement. Le serveur témoin ne prend pas les données hôte ou de mise en miroir pour les serveurs de conversation permanente, mais elle garantit qu’un seul serveur SQL dans une configuration de mise en miroir SQL Server active à tout moment.
  
Cliquez sur **Nouveau** pour définir un nouveau témoin SQL Server éventuellement une instance pour le serveur SQL de conversation permanente en témoin de mise en miroir.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Une fois que vous avez fini d’entrer les options de configuration de magasin SQL Server de ce pool et de procéder à la définition du pool de serveurs de conversation permanente, cliquez sur **suivant** .
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.
  
## <a name="see-also"></a>Voir aussi

[Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Ajouter des serveurs de conversation permanente à votre Skype pour Business Server 2015 topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
