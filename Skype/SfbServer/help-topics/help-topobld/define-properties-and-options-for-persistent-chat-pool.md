---
title: Définir les propriétés et les options de pool de conversations permanentes
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
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Vous configurez les options de votre serveur de conversation permanente ou de votre pool de serveurs de conversation permanente en définissant les propriétés suivantes :'
ms.openlocfilehash: 8d3cef04d7089ffff640740bb048ca52cf7fd91e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218545"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Définir les propriétés et les options de pool de conversations permanentes
 
Vous configurez les options de votre serveur de conversation permanente ou de votre pool de serveurs de conversation permanente en définissant les propriétés suivantes :
  
 **Nom complet du pool de conversations permanentes**: propriété obligatoire définissant un nom convivial qui s’affichera pour ce serveur de conversation permanente ou ce pool de serveurs de conversation permanente.
  
 **Port de conversation permanente**: propriété obligatoire qui définit le numéro de port sur lequel le serveur de conversation permanente ou le pool de serveurs de conversation permanente écoute.
  
 **Activer la conformité**: activez cette case à cocher si vous envisagez de déployer et d’implémenter la fonctionnalité et la base de données de conformité de conversation permanente facultatives.
  
 **Utiliser des magasins SQL Server de sauvegarde pour activer la récupération d’urgence**: activez cette case à cocher si vous envisagez de déployer et d’implémenter la récupération d’urgence des magasins SQL Server de conversation permanente à partir d’un jeu de banques de sauvegarde configuré sur un autre serveur SQL Server. Pour plus d’informations, reportez-vous à la rubrique [configure High Availability and Disaster Recovery for persistent Chat Server in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Cette option est disponible uniquement pour les pools avec plusieurs serveurs. 
  
 **Utiliser ce pool comme serveur par défaut pour \<site that this server or pool is being configured in\> le site **: activez cette case à cocher s’il s’agit du pool de serveurs de conversation permanente ou de conversation permanente par défaut pour le site. Vous devez disposer d’un serveur de conversation permanente par défaut ou de Pol par site.
  
> [!NOTE]
> Si votre topologie comprend plusieurs sites, une case à cocher **utiliser ce pool comme valeur par défaut pour tous les sites** s’affiche également.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Une fois que vous avez terminé d’entrer les options pour ce pool, cliquez sur **suivant** pour continuer avec la définition de pool de serveurs de conversation permanente.
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et mettre fin à l’Assistant **Définir un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active, par exemple.
  
## <a name="see-also"></a>Voir aussi

[Planifier le serveur de conversation permanente dans Skype entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Ajouter un serveur de conversation permanente à votre topologie Skype entreprise Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
