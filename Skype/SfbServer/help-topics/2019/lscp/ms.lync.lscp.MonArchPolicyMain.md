---
title: Stratégie d’archivage
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 'Les stratégies d’archivage permettent d’activer et de désactiver l’archivage pour les utilisateurs hébergés sur Skype entreprise Server. Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’un des éléments suivants ou les deux :'
ms.openlocfilehash: bdeb7925256e47ac61d0210e1be36e28dbdfc0d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291942"
---
# <a name="archiving-policy"></a>Stratégie d’archivage
 
Les stratégies d’archivage permettent d’activer et de désactiver l’archivage pour les utilisateurs hébergés sur Skype entreprise Server. Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’un des éléments suivants ou les deux :
  
- Communications internes
    
- Communications externes (communications qui incluent au moins un utilisateur situé en dehors de votre réseau interne)
    
Les stratégies d’archivage incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies d’archivage de site et utilisateur :
  
- **Politique globale** La stratégie globale est créée par défaut dans tous les déploiements. Vous pouvez modifier la stratégie globale, mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.
    
- **Stratégie de site (facultatif)** Vous pouvez spécifier une ou plusieurs stratégies d’archivage de site que vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un site unique. Une stratégie de site remplace la stratégie globale, mais uniquement pour les sites spécifiés dans vos stratégies d’archivage de site. Vous pouvez modifier ou supprimer les stratégies de site.
    
- **Stratégie utilisateur (facultatif)** Vous pouvez spécifier une ou plusieurs stratégies d’archivage des utilisateurs, qui peuvent chacune être configurées pour activer et désactiver l’archivage des communications internes ou externes d’un utilisateur ou d’un groupe d’utilisateurs spécifiques. Une stratégie utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour les utilisateurs et les groupes d’utilisateurs auxquels vous attribuez des stratégies d’archivage de niveau utilisateur. Vous pouvez modifier ou supprimer les stratégies utilisateur.
    
> [!NOTE]
> Les stratégies d’archivage s’appliquent uniquement aux utilisateurs hébergés sur Skype entreprise Server. Si vous utilisez l’intégration Exchange pour stocker les données d’archivage dans Microsoft Exchange, les stratégies Exchange contrôlent l’archivage pour les utilisateurs hébergés sur Exchange. Pour activer l’archivage de ces utilisateurs, la boîte aux lettres de l’utilisateur doit être placée sur une conservation inaltérable. 
  
La page **Stratégie d’archivage** répertorie toutes les stratégies d’archivage configurées pour votre déploiement. Elle indique également le nom de stratégie, l’étendue (globale, de site ou utilisateur) et les options d’archivage activées pour chaque stratégie d’archivage. La page **Stratégie d’archivage** propose les options suivantes :
- **Nouvelle** Vous pouvez ajouter une ou plusieurs des stratégies d’archivage facultatives suivantes:
    
  - Stratégie de site
    
  - Stratégie utilisateur
    
- **Modifier** Vous pouvez modifier les options de toutes les stratégies d’archivage répertoriées sur la page. Cette option vous permet d’effectuer les opérations suivantes:
    
  - **Afficher les détails** : cette option affiche une boîte de dialogue qui permet de modifier les options d’archivage pour une stratégie d’archivage.
    
  - **Sélectionner tout** : cette option sélectionne toutes les stratégies d’archivage répertoriées.
    
  - **Supprimer** : cette option supprime toutes les stratégies d’archivage sélectionnées.
    
- **Action** Vous pouvez utiliser cette option pour activer ou désactiver rapidement l’archivage des communications internes ou externes dans n’importe quelle stratégie figurant sur la page, au lieu de modifier la stratégie. Les options disponibles sous **action** dépendent de l’option actuellement spécifiée dans la stratégie d’archivage. Toutes les options sont disponibles, à l’exception de l’option actuellement appliquée à la stratégie d’archivage. Les options disponibles sont les suivantes:
    
  - **Activer l’archivage des communications internes**
    
  - **Désactiver l’archivage des communications internes**
    
  - **Activer l’archivage des communications externes**
    
  - **Désactiver l’archivage des communications externes**
    
- **Actualiser** Vous pouvez actualiser la page de **stratégie** d’archivage pour vérifier l’état des options de toutes les stratégies d’archivage.
    
Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, notamment l’intégration d’Exchange, reportez-vous à la rubrique [planification de l’archivage dans Skype entreprise Server](../../../plan-your-deployment/archiving/archiving.md), [déploiement de l’archivage pour Skype entreprise Server](../../../deploy/deploy-archiving/deploy-archiving.md)et [gestion de l’archivage dans Skype entreprise. Serveur](../../../manage/archiving/archiving.md).

