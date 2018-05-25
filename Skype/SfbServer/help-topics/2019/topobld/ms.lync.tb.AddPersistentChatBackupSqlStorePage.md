---
title: Ajouter un magasin SQL Server de stockage de conversation permanente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Vous configurez les magasins de sauvegarde SQL Server qui fourniront des bases de données de sauvegarde pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.
ms.openlocfilehash: 67dc09cca54f0079fc4b7bac16355bbd8dc64633
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>Ajouter un magasin SQL Server de stockage de conversation permanente
 
Vous configurez les magasins de sauvegarde SQL Server qui fourniront des bases de données de sauvegarde pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.
  
 **Magasin SQL Server**: sélectionnez un serveur SQL Server existant et éventuellement une instance de conversation permanente.
  
Cliquez sur **Nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour les données de sauvegarde de conversation permanente.
  
Activez la case à cocher **Activer magasin SQL Server de mise en miroir** pour configurer une base de données SQL Server et une instance facultative qui fournira une base de données en miroir pour les données de sauvegarde de conversation permanente.
  
Sélectionnez dans la liste **magasin SQL Server de la mise en miroir** un serveur SQL Server et une instance facultative agir en tant que miroir SQL Server pour la conversation permanente sauvegarde SQL Server.
  
Cliquez sur **Nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour la mise en miroir du serveur SQL de la conversation permanente.
  
Sélectionnez la liste **utiliser SQL Server témoin pour activer le basculement automatique de mise en miroir** SQL Server qui jouera le rôle de serveur témoin dans les scénarios de basculement. Le serveur témoin ne prend pas les données hôte ou de mise en miroir pour les serveurs de conversation permanente, mais elle garantit qu’un seul serveur SQL dans une configuration de mise en miroir SQL Server active à tout moment.
  
Cliquez sur **Nouveau** pour définir un nouveau témoin SQL Server éventuellement une instance pour la conversation permanente sauvegarde SQL Server témoin de mise en miroir.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Une fois que vous avez fini d’entrer les options de configuration de la banque de ce pool de sauvegarde SQL Server et de procéder à la définition du pool de serveurs de conversation permanente, cliquez sur **suivant** .
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.
  
## <a name="see-also"></a>Voir aussi

#### 

[Planifier pour le serveur de conversation permanente dans Skype Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Configuration matérielle et logicielle requise pour Persistent Chat Server dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurer une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

