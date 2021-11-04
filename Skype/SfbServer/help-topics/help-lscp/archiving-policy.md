---
title: Stratégie d’archivage
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
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Vous utilisez les stratégies d’archivage pour activer et désactiver l’archivage pour les utilisateurs Skype Entreprise Server. Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’une des opérations suivantes ou les deux :'
ms.openlocfilehash: 37452d6bc5274aad19508522bef60ec23e363fe4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60757536"
---
# <a name="archiving-policy"></a>Stratégie d’archivage
 
Vous utilisez les stratégies d’archivage pour activer et désactiver l’archivage pour les utilisateurs Skype Entreprise Server. Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’une des opérations suivantes ou les deux :
  
- Communications internes
    
- Communications externes (communications qui incluent au moins un utilisateur en dehors de votre réseau interne)
    
Les stratégies d’archivage incluent la stratégie globale et, éventuellement, une ou plusieurs stratégies d’archivage de site et d’utilisateur :
  
- **Stratégie globale** La stratégie globale est créée par défaut dans tous les déploiements. Vous pouvez modifier la stratégie globale mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont réinitialisées.
    
- **Stratégie de site (facultatif)** Vous pouvez spécifier une ou plusieurs stratégies d’archivage de site, que vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un site unique. Une stratégie de site remplace la stratégie globale, mais uniquement pour les sites spécifiés dans vos stratégies de site d’archivage. Vous pouvez modifier ou supprimer les stratégies de site.
    
- **Stratégie utilisateur (facultative)** Vous pouvez spécifier une ou plusieurs stratégies d’archivage utilisateur, que vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un utilisateur ou un groupe d’utilisateurs spécifique. Une stratégie utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour les utilisateurs et les groupes d’utilisateurs auxquels vous attribuez des stratégies d’archivage au niveau de l’utilisateur. Vous pouvez modifier ou supprimer les stratégies utilisateur.
    
> [!NOTE]
> Les stratégies d’archivage s’appliquent uniquement aux utilisateurs Skype Entreprise Server. Si vous utilisez l’intégration Exchange pour stocker des données d’archivage dans Microsoft Exchange, les stratégies Exchange 2013 contrôlent l’archivage pour les utilisateurs Exchange 2013. Pour activer l’archivage pour ces utilisateurs, la boîte aux lettres de l’utilisateur doit être placée en In-Place archive. 
  
La page **Stratégie d’archivage** répertorie chaque stratégie d’archivage configurée pour votre déploiement. Il indique également le nom de la stratégie, l’étendue (globale, de site ou utilisateur) et les options d’archivage activées pour chaque stratégie d’archivage. Dans la page **Stratégie d’archivage,** vous avez les options suivantes :
- **Nouveau** Vous pouvez ajouter une ou plusieurs des stratégies d’archivage facultatives suivantes :
    
  - Stratégie de site
    
  - Stratégie utilisateur
    
- **Modifier** Vous pouvez modifier les options de n’importe quelle stratégie d’archivage répertoriée sur la page. À l’aide de cette option, vous pouvez effectuer les opérations suivantes :
    
  - **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’archivage d’une stratégie d’archivage.
    
  - **Sélectionner tout** Cette option sélectionne toutes les stratégies d’archivage de la liste.
    
  - **Supprimer** Cette option supprime toutes les stratégies d’archivage sélectionnées.
    
- **Action** Vous pouvez utiliser cette option pour activer ou désactiver rapidement l’archivage des communications internes ou externes dans n’importe quelle stratégie répertoriée sur la page, au lieu de modifier la stratégie. Les options disponibles sous **Action** dépendent de l’option actuellement spécifiée dans la stratégie d’archivage. Toutes les options sont disponibles, à l’exception de l’option actuellement en vigueur pour la stratégie d’archivage. Les options sont les suivantes :
    
  - **Activer l’archivage des communications internes**
    
  - **Désactiver l’archivage des communications internes**
    
  - **Activer l’archivage des communications externes**
    
  - **Désactiver l’archivage des communications externes**
    
- **Actualiser** Vous pouvez actualiser la page **Stratégie** d’archivage pour vérifier l’état des options de toutes les stratégies d’archivage.
    
Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, notamment l’intégration Exchange, voir Planifier l’archivage dans [Skype Entreprise Server 2015,](../../plan-your-deployment/archiving/archiving.md)Déployer l’archivage pour [Skype Entreprise Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)et Gérer l’archivage dans [Skype Entreprise Server 2015.](../../manage/archiving/archiving.md)

