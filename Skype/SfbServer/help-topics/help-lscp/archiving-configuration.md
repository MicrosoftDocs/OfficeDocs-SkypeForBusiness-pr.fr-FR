---
title: Configuration de l’archivage
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Vous pouvez utiliser les configurations d’archivage pour contrôler les options d’archivage de votre déploiement de Skype entreprise Server, notamment l’activation et la désactivation des options suivantes :'
ms.openlocfilehash: f56b452058a8ce51ac5d5761e9b24c6595bbdd39
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687037"
---
# <a name="archiving-configuration"></a>Configuration de l’archivage
 
Vous pouvez utiliser les configurations d’archivage pour contrôler les options d’archivage de votre déploiement de Skype entreprise Server, notamment l’activation et la désactivation des options suivantes :
  
- Blocage des sessions de messagerie instantanée ou de conférence en cas d’échec de l’archivage
    
- Intégration avec le stockage 2013 Exchange pour les utilisateurs hébergés sur Exchange 2013
    
- Purge des données archivées
    
Les configurations d’archivage incluent la configuration globale, ainsi, éventuellement, qu’une ou plusieurs configurations d’archivage de site ou de pool :
  
- **Configuration globale** La configuration globale est créée par défaut dans tous les déploiements de Skype entreprise Server. Vous pouvez modifier la configuration globale, mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.
    
- **Configuration du site (facultatif)** Vous pouvez spécifier une ou plusieurs configurations d’archivage de site, qui peuvent chacune être configurées pour contrôler les options d’archivage d’un site spécifique. La configuration d’un site remplace la configuration globale, mais uniquement pour les sites spécifiés dans les configurations de site en matière d’archivage. Vous pouvez modifier ou supprimer les configurations de site.
    
- **Configuration du pool (facultatif)** Vous pouvez spécifier une ou plusieurs configurations d’archivage du pool pour contrôler les options d’archivage d’un pool spécifique. Une configuration de pool remplace la configuration globale et la configuration de site, mais seulement pour les pools spécifiés dans les configurations d’archivage de pool. Vous pouvez modifier ou supprimer les configurations de pool.
    
> [!NOTE]
> La configuration de l’archivage s’applique aux utilisateurs hébergés sur Skype entreprise Server et, si vous utilisez Exchange pour stocker les données d’archivage dans Microsoft Exchange, aux utilisateurs hébergés sur Exchange 2013, mais qui sont implémentés de manière légèrement différente pour les utilisateurs hébergés sur Exchange 2013. Ces différences sont décrites dans la section suivante. 
  
La page **Configuration d’archivage** répertorie toutes les stratégies d’archivage configurées pour votre déploiement. Elle indique également le nom de stratégie, l’étendue (globale, de site ou de pool) et les options d’archivage activées pour chaque configuration d’archivage. La page **Configuration d’archivage** propose les options suivantes :
- **Nouvelle** Vous pouvez ajouter une ou plusieurs des configurations d’archivage facultatives suivantes.
    
  - Configuration du site
    
  - Configuration du pool
    
- **Modifier** Vous pouvez modifier les options de n’importe quelle configuration de l’archivage figurant sur la page. Cette option vous permet d’effectuer les opérations suivantes :
    
  - **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’archivage pour la configuration d’archivage sélectionnée. Vous ne pouvez afficher que les détails relatifs à une configuration d’archivage à la fois.
    
  - **Tout sélectionner** Cette option sélectionne toutes les configurations d’archivage dans la liste.
    
  - **Supprimer** Cette option supprime toutes les configurations d’archivage sélectionnées.
    
- **Action** Vous pouvez utiliser cette option pour activer ou désactiver rapidement l’archivage des sessions de messagerie instantanée ou des sessions de conférence Web dans n’importe quelle configuration de la page, au lieu de modifier la configuration. Les options disponibles sous **action** dépendent de l’option actuellement spécifiée dans la configuration de l’archivage. Toutes les options sont disponibles, à l’exception de l’option actuellement appliquée à la configuration de l’archivage. Les options disponibles sont les suivantes :
    
  - **Archiver les sessions de messagerie instantanée**
    
  - **Archiver les sessions de messagerie instantanée et de conférence web**
    
  - **Désactiver l’archivage**
    
- **Actualiser** Vous pouvez actualiser la page Configuration de l' **archivage** pour vérifier l’état des options de toutes les configurations d’archivage.
    
Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, notamment l’intégration d’Exchange, voir [planification de l’archivage dans Skype entreprise server 2015](../../plan-your-deployment/archiving/archiving.md), déploiement de l’archivage [pour skype entreprise Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)et [gestion de l’archivage dans Skype entreprise Server 2015](../../manage/archiving/archiving.md).

