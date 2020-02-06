---
title: Ajouter un magasin SQL Server de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Vous configurez les banques SQL Server qui fournissent des bases de données pour le serveur de chat permanent ou le pool de serveurs de chat permanent.
ms.openlocfilehash: 36939e6192b8d26e5fa84c3c2fe5ef4efe45b577
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820656"
---
# <a name="add-persistent-chat-sql-server-store"></a>Ajouter un magasin SQL Server de conversation permanente
 
Vous configurez les banques SQL Server qui fournissent des bases de données pour le serveur de chat permanent ou le pool de serveurs de chat permanent.
  
 **SQL Server Store**: sélectionnez un serveur SQL Server existant et éventuellement une instance pour la discussion permanente.
  
Cliquez sur **nouveau** pour définir un nouveau serveur SQL et, éventuellement, une nouvelle instance pour les données de conversation permanente.
  
Cochez la case **activer la mise en miroir SQL Server Store** pour configurer une base de données SQL Server et une instance optionnelle qui fournira une base de données en miroir pour les données de conversation persistante.
  
Dans la liste, sélectionnez à partir de la liste **mettre en miroir SQL Server Store** , SQL Server et instance facultative, comme miroir SQL Server pour le serveur SQL chat permanent.
  
Cliquez sur **nouveau** pour définir un nouveau serveur SQL et, si vous le souhaitez, une nouvelle instance de la mise en miroir du serveur de conversation SQL Server.
  
Sélectionnez la liste **utiliser un témoin de mise en miroir SQL Server pour activer le basculement automatique vers** un serveur SQL qui fera office de serveur témoin dans les scénarios de basculement. Le serveur témoin ne met pas en miroir ou n’héberge pas de données pour les serveurs de chat permanent, mais vérifie qu’un seul serveur SQL dans une configuration en miroir est le serveur SQL Server actif à tout moment.
  
Cliquez sur **nouveau** pour définir un nouveau témoin SQL Server éventuellement une instance pour le témoin de mise en miroir SQL Server chat permanent.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Cliquez sur **suivant** lorsque vous avez fini d’entrer les options pour la configuration du magasin SQL Server du pool et continuez avec la définition du pool de serveurs de chat permanent.
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.
  
## <a name="see-also"></a>Voir aussi

[Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Ajouter un serveur de chat permanent à votre topologie 2015 Skype entreprise Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Concepts de base de topologie pour Skype Entreprise Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
