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
description: Vous configurez la magasins SQL Server de conformité qui fournit des bases de données pour le serveur de conversation permanente ou la fonctionnalité de conformité Persistent Chat Server.
ms.openlocfilehash: 3342cea06870ef6841536c9d99e2503745961782
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19503710"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>Ajouter un magasin SQL Server de conformité de conversation permanente
 
Vous configurez la magasins SQL Server de conformité qui fournit des bases de données pour le serveur de conversation permanente ou la fonctionnalité de conformité Persistent Chat Server.
  
 **Magasin SQL Server**: sélectionnez un serveur SQL Server existant et éventuellement une instance de conversation permanente.
  
Cliquez sur **Nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour les données de conformité de conversation permanente.
  
Activez la case à cocher **Activer magasin SQL Server de mise en miroir** pour configurer une base de données SQL Server et une instance facultative qui fournira une base de données en miroir pour les données de conformité de conversation permanente.
  
Sélectionnez dans la liste **magasin SQL Server de la mise en miroir** un serveur SQL Server et une instance facultative agir en tant que miroir SQL Server pour la conformité de conversation permanente SQL Server.
  
Cliquez sur **Nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour la mise en miroir du serveur SQL de la conversation permanente.
  
Sélectionnez la liste **utiliser SQL Server témoin pour activer le basculement automatique de mise en miroir** SQL Server qui jouera le rôle de serveur témoin dans les scénarios de basculement. Le serveur témoin ne prend pas les données hôte ou de mise en miroir pour les serveurs de conversation permanente, mais elle garantit qu’un seul serveur SQL dans une configuration de mise en miroir SQL Server active à tout moment.
  
Cliquez sur **Nouveau** pour définir un nouveau témoin SQL Server éventuellement une instance pour le témoin de mise en miroir SQL Server de conformité de conversation permanente.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Une fois que vous avez fini d’entrer les options de configuration de la banque de ce pool de sauvegarde SQL Server et de procéder à la définition du pool de serveurs de conversation permanente, cliquez sur **suivant** .
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.
  
## <a name="see-also"></a>Voir aussi

[Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Configuration serveur requise pour Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configuration du service de conformité du serveur de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/configure-compliance.md)