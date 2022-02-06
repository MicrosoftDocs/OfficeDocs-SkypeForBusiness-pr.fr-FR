---
title: Ajouter un magasin SQL Server de conversation permanente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Vous configurez les magasins SQL Server qui fourniront des bases de données pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.
---

# <a name="add-persistent-chat-sql-server-store"></a>Ajouter un magasin SQL Server de conversation permanente
 
Vous configurez les magasins SQL Server qui fourniront des bases de données pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.
  
 **SQL Server :** sélectionnez une instance de conversation SQL Server et éventuellement une instance pour la conversation permanente.
  
Cliquez **sur Nouveau** pour définir une nouvelle SQL Server et éventuellement une nouvelle instance pour les données de conversation permanente.
  
Activez **la case à cocher Activer SQL Server** de mise en miroir pour configurer une base de données SQL Server et une instance facultative qui fournira une base de données en miroir pour les données de conversation permanente.
  
Sélectionnez dans la liste **Mise en miroir SQL Server** stocker une instance SQL Server et facultative pour agir en tant que miroir SQL Server pour le SQL Server de conversation permanente.
  
Cliquez **sur Nouveau** pour définir une nouvelle SQL Server et éventuellement une nouvelle instance pour la mise en miroir SQL Server conversation permanente.
  
Sélectionnez la liste Utiliser **SQL Server** témoin de mise en miroir pour activer le SQL Server automatique qui fera fonction de serveur témoin dans les scénarios de failover. Le serveur témoin ne reflète pas ou n’héberge pas de données pour les serveurs de conversation permanente, mais s’assure qu’une seule SQL Server dans une configuration en miroir est la SQL Server active à tout moment.
  
Cliquez **sur Nouveau** pour définir un nouveau témoin SQL Server éventuellement une instance pour le témoin de mise en SQL Server conversation permanente.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Cliquez **sur** Suivant une fois que vous avez terminé d’entrer les options pour la configuration du magasin SQL Server de ce pool et pour passer à la définition du pool de serveurs de conversation permanente.
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et mettre fin à l’Assistant **Définir un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active, par exemple.
  
## <a name="see-also"></a>Voir aussi

[Planifier le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Ajouter un serveur de conversation permanente à votre topologie Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configuration matérielle et logicielle requise pour le serveur de conversation permanente Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Informations de base sur la topologie Skype Entreprise Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
