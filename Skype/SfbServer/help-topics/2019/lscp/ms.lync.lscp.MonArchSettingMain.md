---
title: Configuration de l’archivage
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous utilisez des configurations d’archivage au contrôle options d’archivage pour votre Skype pour le déploiement de serveur d’entreprise, y compris l’activation et désactivation des options suivantes :'
ms.openlocfilehash: 51c77b17fe234ab343fc18f17fce25f2c46813cb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895131"
---
# <a name="archiving-configuration"></a>Configuration de l’archivage
 
Vous utilisez des configurations d’archivage au contrôle options d’archivage pour votre Skype pour le déploiement de serveur d’entreprise, y compris l’activation et désactivation des options suivantes :
  
- Blocage des sessions de messagerie instantanée ou de conférence en cas d’échec de l’archivage
    
- Intégration avec le stockage Exchange, pour les utilisateurs hébergés sur Exchange
    
- Purge des données archivées
    
Les configurations d’archivage incluent la configuration globale, ainsi, éventuellement, qu’une ou plusieurs configurations d’archivage de site ou de pool :
  
- **Configuration globale** La configuration globale créée par défaut dans tous les Skype pour les déploiements de serveur d’entreprise. Vous pouvez modifier la configuration globale, mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.
    
- **Configuration du site (facultative)** Vous pouvez spécifier une ou plusieurs sites d’archivage configurations, que chacun d'entre eux vous pouvez configurer pour contrôler l’archivage des options pour un site spécifique. La configuration d’un site remplace la configuration globale, mais uniquement pour les sites spécifiés dans les configurations de site en matière d’archivage. Vous pouvez modifier ou supprimer les configurations de site.
    
- **Configuration du pool (facultative)** Vous pouvez spécifier un ou plusieurs pool configuration d’archivage, au contrôle options d’archivage d’un pool spécifique. Une configuration de pool remplace la configuration globale et la configuration de site, mais seulement pour les pools spécifiés dans les configurations d’archivage de pool. Vous pouvez modifier ou supprimer les configurations de pool.
    
> [!NOTE]
> Les configurations d’archivage s’appliquent aux utilisateurs hébergés sur Skype pour Business Server et que, si vous utilisez Exchange pour stocker les données d’archivage dans Microsoft Exchange, les utilisateurs hébergés sur Exchange mais sont implémentées différemment pour les utilisateurs hébergés sur Exchange. Ces différences sont décrites dans la section suivante. 
  
La page **Configuration d’archivage** répertorie toutes les stratégies d’archivage configurées pour votre déploiement. Elle indique également le nom de stratégie, l’étendue (globale, de site ou de pool) et les options d’archivage activées pour chaque configuration d’archivage. La page **Configuration d’archivage** propose les options suivantes :
- **Nouveau** Vous pouvez ajouter une ou plusieurs de chacune des configurations d’archivage facultatives suivantes.
    
  - Configuration du site
    
  - Configuration du pool
    
- **Modifier** Vous pouvez modifier les options d’une des configurations d’archivage répertoriées dans la page. Utilisez cette option, vous pouvez procédez comme suit :
    
  - **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’archivage pour la configuration d’archivage sélectionnée. Vous pouvez uniquement afficher les détails pour une configuration d’archivage à la fois.
    
  - **Sélectionner tout** Cette option sélectionne toutes les configurations d’archivage dans la liste.
    
  - **Supprimer** Cette option supprime toutes les configurations d’archivage sélectionnées.
    
- **Action** Vous pouvez utiliser cette option pour activer ou désactiver l’archivage des sessions de messagerie instantanée ou des sessions de conférence web dans n’importe quelle configuration répertoriés dans la page, plutôt qu’une modification de la configuration de rapidement. Les options disponibles sous **Action** dépendent de l’option est actuellement spécifiée dans la configuration d’archivage. Toutes les options sont disponibles, à l’exception de l’option actuellement en vigueur pour la configuration d’archivage. Les options sont les suivantes :
    
  - **Archiver les sessions de messagerie instantanée**
    
  - **Archiver les sessions de messagerie instantanée et de conférence web**
    
  - **Désactiver l’archivage**
    
- **Actualiser** Vous pouvez actualiser la page **Configuration de l’archivage** pour vérifier le statut des options de toutes les configurations d’archivage.
    
Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, y compris l’intégration d’Exchange, voir [planifier l’archivage dans Skype pour Business Server](../../../plan-your-deployment/archiving/archiving.md), [déployer l’archivage pour Skype pour Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)et [gérer l’archivage dans Skype pour les entreprises Serveur](../../../manage/archiving/archiving.md).

