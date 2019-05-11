---
title: Stratégie d’archivage
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Vous utilisez des stratégies d’archivage pour activer et désactiver l’archivage pour les utilisateurs hébergés sur Skype pour Business Server. Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’un des éléments suivants ou les deux :'
ms.openlocfilehash: 03a2645019c083dc3ebdc0c9ca29f4a21d231085
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926135"
---
# <a name="archiving-policy"></a>Stratégie d’archivage
 
Vous utilisez des stratégies d’archivage pour activer et désactiver l’archivage pour les utilisateurs hébergés sur Skype pour Business Server. Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’un des éléments suivants ou les deux :
  
- Communications internes
    
- Communications externes (communications qui incluent au moins un utilisateur situé en dehors de votre réseau interne)
    
Les stratégies d’archivage incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies d’archivage de site et utilisateur :
  
- **Stratégie globale** La stratégie globale est créée par défaut dans tous les déploiements. Vous pouvez modifier la stratégie globale, mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.
    
- **Stratégie de site (facultatif)** Vous pouvez spécifier une ou plusieurs sites d’archivage stratégies, que chacun d'entre eux vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un seul site. Une stratégie de site remplace la stratégie globale, mais uniquement pour les sites spécifiés dans vos stratégies d’archivage de site. Vous pouvez modifier ou supprimer les stratégies de site.
    
- **Stratégie utilisateur (facultatif)** Vous pouvez spécifier des stratégies d’archivage utilisateur un ou plusieurs, que chacun d'entre eux vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un utilisateur spécifique ou un groupe d’utilisateurs. Une stratégie utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour les utilisateurs et les groupes d’utilisateurs auxquels vous attribuez des stratégies d’archivage de niveau utilisateur. Vous pouvez modifier ou supprimer les stratégies utilisateur.
    
> [!NOTE]
> Stratégies d’archivage s’appliquent uniquement aux utilisateurs hébergés sur Skype pour Business Server. Si vous utilisez l’intégration d’Exchange pour stocker les données dans Microsoft Exchange, puis Exchange 2013 stratégies d’archivage contrôle l’archivage pour les utilisateurs hébergés sur Exchange 2013. Pour activer l’archivage pour les utilisateurs, boîte aux lettres de l’utilisateur doit être placé sur le blocage sur Place. 
  
La page **Stratégie d’archivage** répertorie toutes les stratégies d’archivage configurées pour votre déploiement. Elle indique également le nom de stratégie, l’étendue (globale, de site ou utilisateur) et les options d’archivage activées pour chaque stratégie d’archivage. La page **Stratégie d’archivage** propose les options suivantes :
- **Nouveau** Vous pouvez ajouter une ou plusieurs des stratégies d’archivage facultatives suivantes :
    
  - Stratégie de site
    
  - Stratégie utilisateur
    
- **Modifier** Vous pouvez modifier les options d’une des stratégies d’archivage répertoriées sur la page. Utilisez cette option, vous pouvez procédez comme suit :
    
  - **Afficher les détails** : cette option affiche une boîte de dialogue qui permet de modifier les options d’archivage pour une stratégie d’archivage.
    
  - **Sélectionner tout** : cette option sélectionne toutes les stratégies d’archivage répertoriées.
    
  - **Supprimer** : cette option supprime toutes les stratégies d’archivage sélectionnées.
    
- **Action** Vous pouvez utiliser cette option pour activer ou désactiver l’archivage des communications internes ou externes dans toute stratégie répertorié dans la page, plutôt qu’une modification de la stratégie de rapidement. Les options disponibles sous **Action** dépendent de l’option est actuellement spécifiée dans la stratégie d’archivage. Toutes les options sont disponibles, à l’exception de l’option actuellement en vigueur pour la stratégie d’archivage. Les options sont les suivantes :
    
  - **Activer l’archivage des communications internes**
    
  - **Désactiver l’archivage des communications internes**
    
  - **Activer l’archivage des communications externes**
    
  - **Désactiver l’archivage des communications externes**
    
- **Actualiser** Vous pouvez actualiser la page **Stratégie d’archivage** pour vérifier le statut des options de toutes les stratégies d’archivage.
    
Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, y compris l’intégration d’Exchange, voir [planifier l’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [déployer l’archivage pour Skype pour Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)et [gérer l’archivage dans Skype pour Entreprise 2015 Server](../../manage/archiving/archiving.md).

