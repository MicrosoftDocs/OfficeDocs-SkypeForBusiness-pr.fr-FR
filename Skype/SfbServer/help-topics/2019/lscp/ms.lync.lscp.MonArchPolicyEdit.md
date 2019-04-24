---
title: Stratégie d’archivage créer ou modifier une existant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous utilisez des stratégies d’archivage pour contrôler l’archivage des communications internes et externes de votre déploiement pour les utilisateurs qui sont hébergés sur Skype pour Business Server. Les stratégies d’archivage incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies de site et utilisateur :'
ms.openlocfilehash: c43992fe808abf3350fc07ff21b8cbd92a4047a6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215443"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Stratégie d’archivage : création d’une stratégie ou modifier d’une stratégie existante
 
Vous utilisez des stratégies d’archivage pour contrôler l’archivage des communications internes et externes de votre déploiement pour les utilisateurs qui sont hébergés sur Skype pour Business Server. Les stratégies d’archivage incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies de site et utilisateur :
  
- **Stratégie globale** La stratégie globale est créée par défaut dans tous les Skype pour les déploiements de serveur d’entreprise. Vous pouvez modifier la stratégie globale, mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.
    
- **Stratégies de site (facultatifs)** Vous pouvez spécifier une ou plusieurs sites d’archivage stratégies, que chacun d'entre eux vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un site spécifique. Une stratégie de site remplace la stratégie globale, mais uniquement pour les sites spécifiés dans les stratégies d’archivage. Vous pouvez modifier ou supprimer les stratégies de site.
    
- **Stratégies d’utilisateur (facultatifs)** Vous pouvez spécifier des stratégies d’archivage utilisateur un ou plusieurs, que chacun d'entre eux vous pouvez configurer pour activer et désactiver l’archivage pour les communications internes ou externes pour un utilisateur spécifique. Une stratégie utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour le ou les utilisateurs auxquels vous attribuez une stratégie utilisateur. Vous pouvez modifier ou supprimer les stratégies utilisateur.
    
> [!NOTE]
> Si vous utilisez l’intégration d’Exchange pour stocker les données d’archivage dans Microsoft Exchange, Exchange l’archivage de contrôle des stratégies pour les utilisateurs hébergés sur Exchange. Pour activer l’archivage pour les utilisateurs, boîte aux lettres de l’utilisateur doit être placé sur le blocage sur Place. 
  
Pour configurer les paramètres pour une stratégie d’archivage nouvelle ou existante, spécifiez les options suivantes :
- **Nom** Chaque stratégie d’archivage requiert un nom. Le nom est déterminé par le type de stratégie que vous ajoutez ou modifiez :
    
  - **Stratégie globale** Le nom par défaut est Global. Vous pouvez le remplacer par un nom plus descriptif. Par exemple, « Organisation Contoso d’Amérique du Nord".
    
  - **Stratégie de site** Les sites répertoriés dans cette boîte de dialogue incluent tous les sites disponibles dans votre déploiement. Cliquez sur un site individuel pour le sélectionner. Par exemple, Centre de données de Redmond.
    
  - **Stratégie utilisateur** Spécifiez un nom approprié, tel que le nom d’un utilisateur spécifique ou le nom d’un groupe d’utilisateurs ou de l’équipe dans votre organisation. Par exemple, Service juridique.
    
- **Description** Cette étape est facultative. Utilisez-le pour fournir des détails supplémentaires, tels que l’étendue ou l’utilisation de la stratégie. Par exemple, coordonner avec les services juridiques des autres Sites.
    
- **Archiver les communications internes** Activez cette case à cocher pour activer l’archivage des communications sur votre réseau interne. Par défaut, il n’est pas activé dans toutes les stratégies.
    
- **Archiver les communications externes** Activez cette case à cocher pour activer l’archivage des communications qui incluent des utilisateurs externes, tels que les utilisateurs distants, (y compris les utilisateurs anonymes et définition de PIC) et les partenaires fédérés. Par défaut, il n’est pas activé dans toutes les stratégies.
    
Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, y compris l’intégration d’Exchange, voir [planifier l’archivage dans Skype pour Business Server](../../../plan-your-deployment/archiving/archiving.md), [déployer l’archivage pour Skype pour Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)et [gérer l’archivage dans Skype pour les entreprises Serveur](../../../manage/archiving/archiving.md).

