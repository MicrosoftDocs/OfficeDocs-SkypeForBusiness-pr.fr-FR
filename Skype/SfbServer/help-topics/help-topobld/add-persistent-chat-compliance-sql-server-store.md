---
title: Ajouter un magasin SQL Server de conformité de conversation permanente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Vous configurez SQL Server stocke la conformité qui fournira les bases de données pour le serveur de conversation permanente ou de la fonctionnalité de mise en conformité permanent Chat Server.
ms.openlocfilehash: 7854255195e73dcf03ce9027cdd7390c8f4bde54
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>Ajouter un magasin SQL Server de conformité de conversation permanente
 
Vous configurez SQL Server stocke la conformité qui fournira les bases de données pour le serveur de conversation permanente ou de la fonctionnalité de mise en conformité permanent Chat Server.
  
 **Stockage de SQL Server**: sélectionnez un SQL Server existant et éventuellement d’une instance de Chat persistant.
  
Cliquez sur **Nouveau** pour définir une nouvelle de SQL Server et éventuellement une nouvelle instance pour les données de conformité Chat persistant.
  
Activez la case à cocher **mise en miroir de la banque d’informations de SQL Server permettent** de configurer une base de données de SQL Server et l’instance en option qui offre une mise en miroir de la base de données pour les données de conformité Chat persistant.
  
Sélectionnez dans la liste **de SQL Server mise en miroir stocker** une de SQL Server et une instance facultatif en tant que la mise en miroir de SQL Server pour la conformité de conversation permanent de SQL Server.
  
Cliquez sur **Nouveau** pour définir une nouvelle de SQL Server et éventuellement une nouvelle instance de la mise en miroir de SQL Server de la conversation permanent.
  
Sélectionnez la liste **témoin pour permettre le basculement automatique de la mise en miroir de SQL Server d’utiliser** un SQL Server qui jouera le rôle de serveur témoin dans les scénarios de basculement. Le serveur témoin est pas les données en miroir ou d’hôte pour les serveurs Chat persistants, mais garantit que seul SQL Server dans une configuration en miroir est le SQL Server active à tout moment.
  
Cliquez sur **Nouveau** pour définir un nouveau rappel de SQL Server éventuellement une instance pour la conformité de conversation permanent témoin de mise en miroir de SQL Server.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Une fois que vous avez terminé d’entrer les options de configuration de la banque de ce pool de sauvegarde de SQL Server et de procéder à la définition de pool persistant Chat Server, cliquez sur **suivant** .
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.
  
## <a name="see-also"></a>Voir aussi

#### 

[Plan pour un serveur de conversation permanents dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Configuration serveur requise pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Matérielle et logicielle requise pour le serveur Chat persistant dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurer le service de mise en conformité pour serveur de Chat persistant dans Skype pour Business Server 2015](../../manage/persistent-chat/configure-compliance.md)

