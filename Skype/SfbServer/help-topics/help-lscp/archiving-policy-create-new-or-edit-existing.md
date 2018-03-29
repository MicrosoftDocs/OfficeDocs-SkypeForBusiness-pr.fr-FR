---
title: Stratégie d’archivage, créer ou modifier une existante
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 'Les stratégies d’archivage vous permet de contrôler l’archivage des communications internes et externes dans votre déploiement pour les utilisateurs qui sont hébergés sur Skype pour Business Server. Les stratégies d’archivage incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies de site et utilisateur :'
ms.openlocfilehash: af8038371cd421b0232ce2df0ba92aa5b079702e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Stratégie d’archivage : création d’une stratégie ou modifier d’une stratégie existante
 
Les stratégies d’archivage vous permet de contrôler l’archivage des communications internes et externes dans votre déploiement pour les utilisateurs qui sont hébergés sur Skype pour Business Server. Les stratégies d’archivage incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies de site et utilisateur :
  
- **Stratégie globale** La stratégie globale est créée par défaut dans Skype tous les déploiements de serveurs de l’entreprise. Vous pouvez modifier la stratégie globale, mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.
    
- **Stratégies de site (facultatifs)** Vous pouvez spécifier des stratégies d’archivage site un ou plusieurs, que chacun d’eux vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un site spécifique. Une stratégie de site remplace la stratégie globale, mais uniquement pour les sites spécifiés dans les stratégies d’archivage. Vous pouvez modifier ou supprimer les stratégies de site.
    
- **Stratégies de l’utilisateur (facultatifs)** Vous pouvez spécifier des stratégies d’archivage utilisateur un ou plusieurs, que chacun d’eux vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un utilisateur spécifique. Une stratégie utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour le ou les utilisateurs auxquels vous attribuez une stratégie utilisateur. Vous pouvez modifier ou supprimer les stratégies utilisateur.
    
> [!NOTE]
> Si vous utilisez l’intégration de Microsoft Exchange pour stocker, contrôle d’archivage pour les utilisateurs de l’archivage des données dans Microsoft Exchange, puis les stratégies Exchange 2013 hébergé sur Exchange 2013. Pour activer l’archivage pour les utilisateurs, les boîtes aux lettres de l’utilisateur doivent être placés sur Place maintenez. 
  
Pour configurer les paramètres pour une stratégie d’archivage nouvelle ou existante, spécifiez les options suivantes :
- **Nom** Chaque stratégie d’archivage requiert un nom. Le nom est déterminé par le type de stratégie que vous ajoutez ou modifiez :
    
  - **Stratégie globale** Le nom par défaut est Global. Vous pouvez le remplacer par un nom plus descriptif. Par exemple, « Organisation Contoso d’Amérique du Nord".
    
  - **Stratégie de site** Les sites répertoriés dans cette boîte de dialogue incluent tous les sites disponibles dans votre déploiement. Cliquez sur un site individuel pour le sélectionner. Par exemple, Centre de données de Redmond.
    
  - **Stratégie de l’utilisateur** Spécifiez un nom approprié, tel que le nom d’un utilisateur spécifique ou le nom d’un groupe d’utilisateurs ou de l’équipe de votre organisation. Par exemple, Service juridique.
    
- **Description** Cette option est facultative. Elle permet de fournir des détails supplémentaires, tels que l’étendue ou l’utilisation de la stratégie. Par exemple, coordonner avec les services juridiques des autres Sites.
    
- **Archiver les communications internes** Activez cette case à cocher pour activer l’archivage des communications sur votre réseau interne. Par défaut, il n’est pas activé dans n’importe quelle stratégie.
    
- **Archiver les communications externes** Activez cette case à cocher pour activer l’archivage des communications qui incluent les utilisateurs externes, tels que des utilisateurs distants, (y compris les utilisateurs anonymes et définition de PIC) et les partenaires fédérés. Par défaut, il n’est pas activé dans n’importe quelle stratégie.
    
Pour plus d’informations sur la fonctionnalité d’archivage et de fonctionnalités, y compris l’intégration d’Exchange, consultez [planification d’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [déployer l’archivage pour Skype pour Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)et [gérer l’archivage dans Skype pour Entreprise 2015 de serveur](../../manage/archiving/archiving.md).

