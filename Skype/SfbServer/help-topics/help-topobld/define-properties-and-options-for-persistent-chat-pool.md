---
title: Définir les propriétés et les options de pool de conversations permanentes
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Vous configurez les options pour votre serveur de conversation permanente ou un pool de serveurs de conversation permanente en définissant les propriétés suivantes :'
ms.openlocfilehash: 380a1e34e041368d4520cd5c8ecea5b18284ef51
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887542"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Définir les propriétés et les options de pool de conversations permanentes
 
Vous configurez les options pour votre serveur de conversation permanente ou un pool de serveurs de conversation permanente en définissant les propriétés suivantes :
  
 **Nom complet du pool de conversation permanente**: propriété obligatoire qui définit un nom convivial qui s’affichera pour ce serveur de conversation permanente ou un pool de serveurs de conversation permanente.
  
 **Port de conversation permanente**: propriété obligatoire qui définira le port numéro auquel ce serveur de conversation permanente ou Persistent Chat Server pool écoutera.
  
 **Activer la conformité**: activez la case à cocher si vous envisagez de déployer et d’implémenter la fonctionnalité de conformité de conversation permanente facultative et une base de données.
  
 **Stocke les utiliser sauvegarde SQL Server pour activer la récupération d’urgence**: Activez cette case à cocher si vous envisagez de déployer et d’implémenter la récupération d’urgence du serveur SQL conversation permanente stocke à partir d’un jeu de sauvegarde configuré des magasins sur un autre serveur SQL. Pour plus d’informations, voir [configurer une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Cette option n’est disponible que pour les pools comportant plusieurs serveurs. 
  
 **Utiliser ce pool comme valeur par défaut pour le site \<site ce serveur ou ce pool est configuré dans\>**: Activez cette case à cocher s’il s’agit du serveur de conversation permanente par défaut ou du pool Persistent Chat Server pour le site. Vous devez disposer un serveur de conversation permanente par défaut ou pol par site.
  
> [!NOTE]
> Si votre topologie comporte plusieurs sites, la case à cocher **Toujours utiliser ce pool pour tous les sites** s’affiche également.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Une fois que vous avez fini d’entrer les options pour ce pool afin de passer à la définition du pool de serveurs de conversation permanente, cliquez sur **suivant** .
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.
  
## <a name="see-also"></a>Voir aussi

[Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Ajouter des serveurs de conversation permanente à votre Skype pour Business Server 2015 topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
