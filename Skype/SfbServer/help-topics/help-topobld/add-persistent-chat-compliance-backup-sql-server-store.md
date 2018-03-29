---
title: Ajouter un magasin SQL Server de stockage de conformité de conversation permanente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Vous configurez la sauvegarde la conformité que SQL Server stocke qui fournira les bases de données de sauvegarde pour le serveur Chat persistant ou conformité permanente Chat Server que stocke de SQL Server.
ms.openlocfilehash: 4e3a2bf034d5ab20c7352f2b6ef9c8a6a0c4befa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Ajouter un magasin SQL Server de stockage de conformité de conversation permanente
 
Vous configurez la sauvegarde la conformité que SQL Server stocke qui fournira les bases de données de sauvegarde pour le serveur Chat persistant ou conformité permanente Chat Server que stocke de SQL Server.
  
 **Stockage de SQL Server**: sélectionnez un SQL Server existant et éventuellement d’une instance de Chat persistant.
  
Cliquez sur **Nouveau** pour définir une nouvelle de SQL Server et éventuellement une nouvelle instance pour les données de sauvegarde conformité Chat persistant.
  
Activez la case à cocher **mise en miroir de la banque d’informations de SQL Server permettent** de configurer une base de données de SQL Server et l’instance en option qui fournit une base de données en miroir pour les données de sauvegarde conformité Chat persistant.
  
Sélectionnez dans la liste **de SQL Server mise en miroir stocker** une de SQL Server et une instance facultatif en tant que la mise en miroir de SQL Server pour la conformité sauvegarde Chat permanente de SQL Server.
  
Cliquez sur **Nouveau** pour définir une nouvelle de SQL Server et éventuellement une nouvelle instance de la mise en miroir de SQL Server de la conversation permanent.
  
Sélectionnez la liste **témoin pour permettre le basculement automatique de la mise en miroir de SQL Server d’utiliser** un SQL Server qui jouera le rôle de serveur témoin dans les scénarios de basculement. Le serveur témoin est pas les données en miroir ou d’hôte pour les serveurs Chat persistants, mais garantit que seul SQL Server dans une configuration en miroir est le SQL Server active à tout moment.
  
Cliquez sur **Nouveau** pour définir un nouveau rappel de SQL Server éventuellement une instance pour la conformité sauvegarde Chat persistant témoin de mise en miroir de SQL Server.
  
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
  
[Configuration de haute disponibilité et reprise après sinistre pour serveur Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

