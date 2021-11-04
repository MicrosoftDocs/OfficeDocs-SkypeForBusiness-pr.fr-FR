---
title: Définir les propriétés et les options de pool de conversations permanentes
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Vous configurez les options de votre serveur de conversation permanente ou pool de serveurs de conversation permanente en définissant les propriétés suivantes :'
ms.openlocfilehash: 11b4731228f3690ce0fbe2675b5cef35faa3378e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760802"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Définir les propriétés et les options de pool de conversations permanentes
 
Vous configurez les options de votre serveur de conversation permanente ou pool de serveurs de conversation permanente en définissant les propriétés suivantes :
  
 **Nom complet du pool** de conversation permanente : propriété obligatoire qui définit un nom convivial qui sera affiché pour ce serveur de conversation permanente ou ce pool de serveurs de conversation permanente.
  
 **Port de conversation permanente**: propriété obligatoire qui définit le numéro de port que ce serveur de conversation permanente ou ce pool de serveurs de conversation permanente écoutera.
  
 **Activer la conformité**: activez la case à cocher si vous envisagez de déployer et d’implémenter la base de données et la fonctionnalité de conformité de conversation permanente facultatives.
  
 Utilisez les magasins **d’SQL Server** de sauvegarde pour activer la récupération d’urgence : activez cette case à cocher si vous envisagez de déployer et d’implémenter la récupération d’urgence des magasins de SQL Server de conversation permanente à partir d’un ensemble configuré de magasins sur une autre SQL Server. Pour plus d’informations, voir [Configure high availability and disaster recovery for Persistent Chat Server in Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Cette option est disponible uniquement pour les pools avec plusieurs serveurs. 
  
 **Utilisez ce pool par \<site that this server or pool is being configured in\> défaut** pour le site : cochez cette case s’il s’utilise comme serveur de conversation permanente ou pool de serveurs de conversation permanente par défaut pour le site. Vous devez avoir un serveur de conversation permanente ou un serveur de conversation permanente par défaut par site.
  
> [!NOTE]
> Si votre topologie comprend plusieurs sites, une case à cocher utiliser ce pool par défaut pour tous les **sites** s’affiche également.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Cliquez **sur Suivant** une fois que vous avez terminé d’entrer les options de ce pool pour poursuivre la définition du pool de serveurs de conversation permanente.
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et mettre fin à l’Assistant **Définir un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active, par exemple.
  
## <a name="see-also"></a>Voir aussi

[Planifier le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Ajouter un serveur de conversation permanente à votre topologie Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
