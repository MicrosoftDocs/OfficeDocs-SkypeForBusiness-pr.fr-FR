---
title: Ajouter un magasin SQL Server de stockage de conformité de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Vous configurez les banques SQL Server de conformité de sauvegarde qui fournissent des bases de données de sauvegarde pour le serveur de chat permanent ou les magasins SQL Server Compliance Server.
ms.openlocfilehash: 457874f87266453939c75cdef50d30231d8610bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277705"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Ajouter un magasin SQL Server de stockage de conformité de conversation permanente
 
Vous configurez les banques SQL Server de conformité de sauvegarde qui fournissent des bases de données de sauvegarde pour le serveur de chat permanent ou les magasins SQL Server Compliance Server.
  
 **SQL Server Store**: sélectionnez un serveur SQL Server existant et éventuellement une instance pour la discussion permanente.
  
Cliquez sur **nouveau** pour définir un nouveau serveur SQL et, éventuellement, une nouvelle instance pour les données de conformité de la sauvegarde de conversation permanente.
  
Cochez la case **activer la mise en miroir SQL Server Store** pour configurer une base de données SQL Server et une instance optionnelle qui fournira une base de données en miroir pour les données de conformité de la sauvegarde de conversation permanente.
  
Dans la liste, sélectionnez à partir de la liste **mettre en miroir SQL Server Store** un serveur SQL Server et une instance facultative à faire office de miroir SQL Server pour le serveur SQL Server
  
Cliquez sur **nouveau** pour définir un nouveau serveur SQL et, si vous le souhaitez, une nouvelle instance de la mise en miroir du serveur de conversation SQL Server.
  
Sélectionnez la liste **utiliser un témoin de mise en miroir SQL Server pour activer le basculement automatique vers** un serveur SQL qui fera office de serveur témoin dans les scénarios de basculement. Le serveur témoin ne met pas en miroir ou n’héberge pas de données pour les serveurs de chat permanent, mais vérifie qu’un seul serveur SQL dans une configuration en miroir est le serveur SQL Server actif à tout moment.
  
Cliquez sur **nouveau** pour définir un nouveau témoin SQL Server en option une instance pour le témoin de mise en miroir de l’option de mise en miroir SQL Server du serveur Chat.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Cliquez sur **suivant** lorsque vous avez fini d’entrer les options pour la configuration de sauvegarde du magasin SQL Server du pool et de continuer avec la définition du pool de serveurs de chat permanent.
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.
  
## <a name="see-also"></a>Voir aussi

[Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configuration du service de conformité du serveur de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
