---
title: Définir les propriétés et les options de pool de conversations permanentes
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
description: 'Vous configurez les options de votre serveur de Chat permanent ou d’un pool de serveur de conversation persistant en définissant les propriétés suivantes :'
ms.openlocfilehash: 445e84b4be0567b63b9a56a7bc130e584a826430
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Définir les propriétés et les options de pool de conversations permanentes
 
Vous configurez les options de votre serveur de Chat permanent ou d’un pool de serveur de conversation persistant en définissant les propriétés suivantes :
  
 **Nom complet du pool Chat persistant**: une propriété requise qui définit un nom convivial qui s’affiche pour ce serveur de Chat permanent ou d’un pool de serveur de conversation persistant.
  
 **Port de conversation permanent**: une propriété requise qui définit le port numéro que ce serveur de conversation permanent ou pool de serveur de conversation persistant écoutera.
  
 **Conformité**: activez la case à cocher si vous envisagez de déployer et de mettre en œuvre la fonctionnalité de mise en conformité de conversation persistant facultative et de la base de données.
  
 **Utilisez sauvegarde SQL Server stocke pour la reprise après sinistre**: sélectionnez cette case à cocher si vous envisagez de déployer et de mettre en œuvre la reprise après sinistre de la permanente de SQL Server de Chat stocke à partir d’un jeu de sauvegarde configuré de banques sur un autre de SQL Server. Pour plus d’informations, consultez [configurer la haute disponibilité et reprise après sinistre pour serveur Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Cette option n’est disponible que pour les pools comportant plusieurs serveurs. 
  
 **Utiliser ce pool par défaut pour le site \<site que ce serveur ou ce pool est configuré dans\>**: Cochez cette case s’il s’agit par défaut persistante Chat Server ou pool de serveur de conversation persistant pour le site. Il vous faut un serveur de conversation permanent par défaut ou pol par site.
  
> [!NOTE]
> Si votre topologie comporte plusieurs sites, la case à cocher **Toujours utiliser ce pool pour tous les sites** s’affiche également.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Une fois que vous avez terminé d’entrer les options pour ce pool de procéder à la définition de pool persistant Chat Server, cliquez sur **suivant** .
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.
  
## <a name="see-also"></a>Voir aussi

#### 

[Plan pour un serveur de conversation permanents dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Ajouter serveur de Chat permanente à votre Skype pour la topologie de Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

