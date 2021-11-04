---
title: Configuration de l’archivage
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous utilisez les configurations d’archivage pour contrôler les options d’archivage de votre déploiement Skype Entreprise Server, notamment l’activation et la désactivation des options suivantes :'
ms.openlocfilehash: f67e43d42bb13f0d0c192f7ac9a2710e05578ed5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773024"
---
# <a name="archiving-configuration"></a>Configuration de l’archivage
 
Vous utilisez les configurations d’archivage pour contrôler les options d’archivage de votre déploiement Skype Entreprise Server, notamment l’activation et la désactivation des options suivantes :
  
- Blocage des sessions de messagerie instantanée ou de conférence en cas d’échec de l’archivage
    
- Intégration au stockage Exchange, pour les utilisateurs Exchange
    
- Purge des données archivées
    
Les configurations d’archivage incluent la configuration globale et éventuellement une ou plusieurs configurations d’archivage de site ou de pool :
  
- **Configuration globale** La configuration globale est créée par défaut dans tous Skype Entreprise Server déploiements. Vous pouvez modifier la configuration globale mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont réinitialisées.
    
- **Configuration du site (facultatif)** Vous pouvez spécifier une ou plusieurs configurations d’archivage de site, que vous pouvez configurer pour contrôler les options d’archivage d’un site spécifique. La configuration d’un site remplace la configuration globale, mais uniquement pour les sites spécifiés dans les configurations de site en matière d’archivage. Vous pouvez modifier ou supprimer des configurations de site.
    
- **Configuration du pool (facultatif)** Vous pouvez spécifier une ou plusieurs configurations d’archivage de pool pour contrôler les options d’archivage d’un pool spécifique. Une configuration de pool supplante la configuration globale et la configuration de site, mais seulement pour les pools spécifiés dans les configurations d’archivage de pool. Vous pouvez modifier ou supprimer les configurations de pool.
    
> [!NOTE]
> Les configurations d’archivage s’appliquent aux utilisateurs stockés sur Skype Entreprise Server et, si vous utilisez Exchange pour stocker des données d’archivage dans Microsoft Exchange, aux utilisateurs d’accueil sur Exchange mais sont implémentés légèrement différemment pour les utilisateurs d’Exchange. Ces différences sont décrites dans la section suivante. 
  
La page **Configuration d’archivage** répertorie toutes les stratégies d’archivage configurées pour votre déploiement. Elle indique également le nom de stratégie, l’étendue (globale, de site ou de pool) et les options d’archivage activées pour chaque configuration d’archivage. La page **Configuration d’archivage** propose les options suivantes :
- **Nouveau** Vous pouvez ajouter une ou plusieurs des configurations d’archivage facultatives suivantes.
    
  - Configuration du site
    
  - Configuration du pool
    
- **Modifier** Vous pouvez modifier les options de toutes les configurations d’archivage répertoriées sur la page. À l’aide de cette option, vous pouvez effectuer les opérations suivantes :
    
  - **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’archivage pour la configuration d’archivage sélectionnée. Vous ne pouvez afficher les détails que pour une configuration d’archivage à la fois.
    
  - **Sélectionner tout** Cette option sélectionne toutes les configurations d’archivage dans la liste.
    
  - **Supprimer** Cette option supprime toutes les configurations d’archivage sélectionnées.
    
- **Action** Vous pouvez utiliser cette option pour activer ou désactiver rapidement l’archivage des sessions de messagerie instantanée ou des sessions de conférence web dans n’importe quelle configuration répertoriée sur la page, au lieu de modifier la configuration. Les options disponibles sous **Action** dépendent de l’option actuellement spécifiée dans la configuration de l’archivage. Toutes les options sont disponibles, à l’exception de l’option actuellement en vigueur pour la configuration de l’archivage. Les options sont les suivantes :
    
  - **Archiver les sessions de messagerie instantanée**
    
  - **Archiver les sessions de messagerie instantanée et de conférence web**
    
  - **Désactiver l’archivage**
    
- **Actualiser** Vous pouvez actualiser la page **Configuration de l’archivage** pour vérifier l’état des options de toutes les configurations d’archivage.
    
Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, notamment l’intégration Exchange, voir Planifier l’archivage dans [Skype Entreprise Server,](../../../plan-your-deployment/archiving/archiving.md)Déployer l’archivage pour [Skype Entreprise Server](../../../deploy/deploy-archiving/deploy-archiving.md)et Gérer l’archivage [dans Skype Entreprise Server ](../../../manage/archiving/archiving.md).

