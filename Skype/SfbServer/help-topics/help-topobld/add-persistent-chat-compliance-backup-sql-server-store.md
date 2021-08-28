---
title: Ajouter un magasin SQL Server de sauvegarde de conformité de conversation permanente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Vous configurez les magasins de SQL Server de conformité de sauvegarde qui fourniront des bases de données de sauvegarde pour les magasins de conformité du serveur de conversation permanente ou du SQL Server de conversation permanente.
ms.openlocfilehash: b15cfb3ed23147bb6a6c9e2ea816350343cadf72
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615770"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Ajouter un magasin SQL Server de sauvegarde de conformité de conversation permanente
 
Vous configurez les magasins de SQL Server de conformité de sauvegarde qui fourniront des bases de données de sauvegarde pour les magasins de conformité du serveur de conversation permanente ou du SQL Server de conversation permanente.
  
 **SQL Server :** sélectionnez une instance de conversation SQL Server et éventuellement une instance pour la conversation permanente.
  
Cliquez **sur Nouveau** pour définir une nouvelle SQL Server et éventuellement une nouvelle instance pour les données de conformité de sauvegarde de conversation permanente.
  
Activez la case à **cocher Activer SQL Server** de mise en miroir pour configurer une base de données SQL Server et une instance facultative qui fournira une base de données en miroir pour les données de conformité de sauvegarde de conversation permanente.
  
Dans la liste Mise en **miroir SQL Server** stockez une instance SQL Server et facultative pour agir en tant que miroir SQL Server pour le service de conformité de la SQL Server de conversation permanente.
  
Cliquez **sur** Nouveau pour définir une nouvelle SQL Server et éventuellement une nouvelle instance pour la mise en miroir SQL Server conversation permanente.
  
Sélectionnez la liste Utiliser **SQL Server** témoin de mise en miroir pour activer le SQL Server automatique qui fera fonction de serveur témoin dans les scénarios de failover. Le serveur témoin ne reflète pas ou n’héberge pas de données pour les serveurs de conversation permanente, mais s’assure qu’une seule SQL Server dans une configuration en miroir est la SQL Server active à tout moment.
  
Cliquez **sur Nouveau** pour définir un nouveau témoin SQL Server éventuellement une instance pour la conformité de la sauvegarde de conversation permanente SQL Server témoin de mise en miroir.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Cliquez **sur** Suivant une fois que vous avez terminé d’entrer les options de sauvegarde de ce pool SQL Server configuration du magasin et pour passer à la définition du pool de serveurs de conversation permanente.
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et mettre fin à l’Assistant **Définir un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active, par exemple.
  
## <a name="see-also"></a>Voir aussi

[Planifier le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Configuration matérielle et logicielle requise pour le serveur de conversation permanente Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurer le service de conformité pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
