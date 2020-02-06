---
title: Ajouter un magasin SQL Server de conformité de conversation permanente
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
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Vous configurez les magasins SQL Server de conformité qui fournissent des bases de données pour le serveur de chat permanent ou la fonctionnalité de conformité du serveur de chat permanent.
ms.openlocfilehash: fd51b3d582c915d02799f2f633869e84f3659c4f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820686"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>Ajouter un magasin SQL Server de conformité de conversation permanente
 
Vous configurez les magasins SQL Server de conformité qui fournissent des bases de données pour le serveur de chat permanent ou la fonctionnalité de conformité du serveur de chat permanent.
  
 **SQL Server Store**: sélectionnez un serveur SQL Server existant et éventuellement une instance pour la discussion permanente.
  
Cliquez sur **nouveau** pour définir un nouveau serveur SQL et, éventuellement, une nouvelle instance pour les données de conformité permanentes.
  
Activez la case à cocher **activer la mise en miroir SQL Server Store** pour configurer une base de données SQL Server et une instance optionnelle qui fournira une base de données en miroir pour les données de mise en conformité des conversations permanentes.
  
Dans la liste, sélectionnez à partir de la liste **mettre en miroir SQL Server Store** , SQL Server et instance facultative, comme miroir SQL Server pour le serveur SQL Server Compliance chat.
  
Cliquez sur **nouveau** pour définir un nouveau serveur SQL et, si vous le souhaitez, une nouvelle instance de la mise en miroir du serveur de conversation SQL Server.
  
Sélectionnez la liste **utiliser un témoin de mise en miroir SQL Server pour activer le basculement automatique vers** un serveur SQL qui fera office de serveur témoin dans les scénarios de basculement. Le serveur témoin ne met pas en miroir ou n’héberge pas de données pour les serveurs de chat permanent, mais vérifie qu’un seul serveur SQL dans une configuration en miroir est le serveur SQL Server actif à tout moment.
  
Cliquez sur **nouveau** pour définir un nouveau témoin SQL Server en option une instance pour le témoin de mise en miroir SQL Server en conformité avec les conversations permanentes.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Cliquez sur **suivant** lorsque vous avez fini d’entrer les options pour la configuration de sauvegarde du magasin SQL Server du pool et de continuer avec la définition du pool de serveurs de chat permanent.
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.
  
## <a name="see-also"></a>Voir aussi

[Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configuration du service de conformité du serveur de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/configure-compliance.md)
