---
title: Ajouter un magasin SQL Server de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Vous configurez les magasins SQL Server qui fourniront des bases de données pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.
ms.openlocfilehash: 2771b63063e155973cd711c4b80f06dee46e1865
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216325"
---
# <a name="add-persistent-chat-sql-server-store"></a>Ajouter un magasin SQL Server de conversation permanente
 
Vous configurez les magasins SQL Server qui fourniront des bases de données pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.
  
 **Magasin SQL Server**: sélectionnez un serveur SQL Server existant et, éventuellement, une instance pour la conversation permanente.
  
Cliquez sur **nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour les données de conversation permanente.
  
Activez la case à cocher **activer la mise en miroir du magasin SQL Server** pour configurer une base de données SQL Server et une instance facultative qui fournira une base de données mise en miroir pour les données de conversation permanente.
  
Dans la liste **magasin SQL Server de mise en miroir** , sélectionnez un serveur SQL Server et une instance facultative pour agir en tant que miroir SQL Server pour le serveur SQL Server de conversation permanente.
  
Cliquez sur **nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour la mise en miroir SQL Server de conversation permanente.
  
Sélectionnez la liste **utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** un serveur SQL qui fera office de serveur témoin dans les scénarios de basculement. Le serveur témoin ne met pas en miroir ou n’héberge pas de données pour les serveurs de conversation permanente, mais garantit qu’un seul serveur SQL Server dans une configuration mise en miroir est le serveur SQL actif à tout moment.
  
Cliquez sur **nouveau** pour définir un nouveau témoin SQL Server, éventuellement une instance pour le témoin de mise en miroir SQL Server de conversation permanente.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Une fois que vous avez terminé d’entrer les options pour la configuration du magasin SQL Server de ce pool, cliquez sur **suivant** pour continuer la définition du pool de serveurs de conversation permanente.
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et mettre fin à l’Assistant **Définir un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active, par exemple.
  
## <a name="see-also"></a>Voir aussi

[Planifier le serveur de conversation permanente dans Skype entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Ajouter un serveur de conversation permanente à votre topologie Skype entreprise Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configuration requise pour le serveur pour Skype entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Concepts de base de la topologie pour Skype entreprise Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype entreprise Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
