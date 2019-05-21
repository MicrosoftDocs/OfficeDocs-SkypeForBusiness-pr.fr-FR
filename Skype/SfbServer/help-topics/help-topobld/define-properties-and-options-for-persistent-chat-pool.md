---
title: Définir les propriétés et les options de pool de conversations permanentes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Vous pouvez configurer les options pour votre serveur de chat permanent ou le pool de serveurs de chat permanent en définissant les propriétés suivantes:'
ms.openlocfilehash: f719a4c76be88dd571c551645bacd13ef22e9a19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306142"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Définir les propriétés et les options de pool de conversations permanentes
 
Vous pouvez configurer les options pour votre serveur de chat permanent ou le pool de serveurs de chat permanent en définissant les propriétés suivantes:
  
 **Nom d’affichage du pool de conversations permanentes**: propriété requise définissant un nom convivial qui sera affiché pour ce serveur de chat permanent ou le pool de serveurs de chat permanent.
  
 **Port de chat permanent**: propriété requise définissant le numéro de port que le serveur de chat permanent ou le pool de serveurs de chat permanent écoutera.
  
 **Activer la conformité**: activez la case à cocher si vous envisagez de déployer et d’implémenter la fonctionnalité et la base de données de compatibilité de conversation persistante facultative.
  
 **Utiliser les magasins de sauvegarde SQL Server pour activer la reprise après sinistre**: activez cette case à cocher si vous envisagez de déployer et de mettre en œuvre une reprise après sinistre des magasins SQL Server de discussion persistante à partir d’un jeu de stockage de sauvegarde configuré sur un autre serveur SQL Server. Pour plus d’informations, reportez-vous à la rubrique Configuration de la [haute disponibilité et de la reprise après sinistre pour le serveur Chat permanent dans Skype entreprise server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Cette option n’est disponible que pour les pools comportant plusieurs serveurs. 
  
 **Utilisez ce pool par défaut pour le site \<de site\>sur lequel ce serveur ou ce pool est configuré**: activez cette case à cocher s’il s’agit du serveur de chat permanent par défaut ou du pool de serveurs de chat permanent pour le site. Vous devez disposer d’une conversation permanente par défaut ou d’un serveur. pol par site.
  
> [!NOTE]
> Si votre topologie comporte plusieurs sites, la case à cocher **Toujours utiliser ce pool pour tous les sites** s’affiche également.
  
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Cliquez sur **suivant** une fois que vous avez terminé d’entrer les options pour ce pool et continuez avec la définition du pool de serveurs de chat permanent.
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.
  
## <a name="see-also"></a>Voir aussi

[Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Ajouter un serveur de chat permanent à votre topologie 2015 Skype entreprise Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
