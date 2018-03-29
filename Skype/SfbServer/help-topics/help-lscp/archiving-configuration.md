---
title: Configuration de l’archivage
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Vous utilisez des configurations d’archivage au contrôle de l’archivage des options pour votre Skype pour le déploiement de serveur d’entreprise, y compris l’activation et la désactivation des options suivantes :'
ms.openlocfilehash: e32c42d5ef945b360ce4992ea9a33658bcc4068a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-configuration"></a>Configuration de l’archivage
 
Vous utilisez des configurations d’archivage au contrôle de l’archivage des options pour votre Skype pour le déploiement de serveur d’entreprise, y compris l’activation et la désactivation des options suivantes :
  
- Blocage des sessions de messagerie instantanée ou de conférence en cas d’échec de l’archivage
    
- Intégration avec le stockage Exchange 2013, pour les utilisateurs hébergés sur Exchange 2013
    
- Purge des données archivées
    
Les configurations d’archivage incluent la configuration globale, ainsi, éventuellement, qu’une ou plusieurs configurations d’archivage de site ou de pool :
  
- **Configuration globale** La configuration globale est créée par défaut dans Skype tous les déploiements de serveurs de l’entreprise. Vous pouvez modifier la configuration globale, mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.
    
- **Configuration du site (facultative)** Vous pouvez spécifier une ou plusieurs site d’archivage configurations, que chacun d'entre eux vous pouvez configurer pour contrôler les options pour un site spécifique d’archivage. La configuration d’un site remplace la configuration globale, mais uniquement pour les sites spécifiés dans les configurations de site en matière d’archivage. Vous pouvez modifier ou supprimer les configurations de site.
    
- **Configuration de pool (facultatif)** Vous pouvez spécifier un ou plusieurs pool configuration d’archivage, pour contrôler les options d’un pool spécifique d’archivage. Une configuration de pool remplace la configuration globale et la configuration de site, mais seulement pour les pools spécifiés dans les configurations d’archivage de pool. Vous pouvez modifier ou supprimer les configurations de pool.
    
> [!NOTE]
> Configurations d’archivage qui s’appliquent aux utilisateurs hébergés sur Skype pour Business Server et que, si vous utilisez Exchange pour stocker les données d’archivage dans Microsoft Exchange, pour les utilisateurs hébergés sur Exchange 2013, mais sont implémentées légèrement différemment pour les utilisateurs hébergés sur Exchange 2013. Ces différences sont décrites dans la section suivante. 
  
La page **Configuration d’archivage** répertorie toutes les stratégies d’archivage configurées pour votre déploiement. Elle indique également le nom de stratégie, l’étendue (globale, de site ou de pool) et les options d’archivage activées pour chaque configuration d’archivage. La page **Configuration d’archivage** propose les options suivantes :
- **Nouveau** Vous pouvez ajouter un ou plusieurs de chacune des configurations facultatives suivantes d’archivage.
    
  - Configuration du site
    
  - Configuration du pool
    
- **Modifier** Vous pouvez modifier les options d’une des configurations d’archivage répertoriées sur la page. À l’aide de cette option, vous pouvez effectuer les opérations suivantes :
    
  - **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’archivage pour la configuration de l’archivage sélectionnée. Vous ne pouvez afficher les détails d’une configuration d’archivage à une heure.
    
  - **Sélectionner tout** Cette option permet de sélectionner toutes les configurations d’archivage dans la liste.
    
  - **Supprimer** Cette option supprime toutes les configurations d’archivage sélectionnées.
    
- **Action** Vous pouvez utiliser cette option pour activer ou désactiver l’archivage des sessions de messagerie instantanée ou des sessions de conférence web dans n’importe quelle configuration répertoriés sur la page, au lieu de modifier la configuration rapidement. Les options disponibles sous **Action** dépendent de l’option est actuellement spécifiée dans la configuration de l’archivage. Toutes les options sont disponibles, à l’exception de l’option actuellement en vigueur pour la configuration de l’archivage. Contient les options suivantes :
    
  - **Archiver les sessions de messagerie instantanée**
    
  - **Archiver les sessions de messagerie instantanée et de conférence web**
    
  - **Désactiver l’archivage**
    
- **Actualiser** Vous pouvez actualiser la page de **Configuration de l’archivage** pour vérifier l’état des options de toutes les configurations de l’archivage.
    
Pour plus d’informations sur la fonctionnalité d’archivage et de fonctionnalités, y compris l’intégration d’Exchange, consultez [planification d’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [déployer l’archivage pour Skype pour Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)et [gérer l’archivage dans Skype pour Entreprise 2015 de serveur](../../manage/archiving/archiving.md).

