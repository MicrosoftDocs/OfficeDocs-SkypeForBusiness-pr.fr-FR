---
title: 'Stratégie d’archivage : création d’une stratégie ou modification d’une stratégie existante'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 'Vous utilisez des stratégies d’archivage pour contrôler l’archivage des communications internes et externes dans votre déploiement pour les utilisateurs qui sont Skype Entreprise Server. Les stratégies d’archivage incluent la stratégie globale, ainsi qu’éventuellement une ou plusieurs stratégies de site et utilisateur :'
ms.openlocfilehash: f50288ac1890cf3768b2b14164b9d4b2ddc78eece97767a58f41a2b072c48724
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278822"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Stratégie d’archivage : création d’une nouvelle ou modification d’une stratégie existante
 
Vous utilisez des stratégies d’archivage pour contrôler l’archivage des communications internes et externes dans votre déploiement pour les utilisateurs qui sont Skype Entreprise Server. Les stratégies d’archivage incluent la stratégie globale, ainsi qu’éventuellement une ou plusieurs stratégies de site et utilisateur :
  
- **Stratégie globale** La stratégie globale est créée par défaut dans tous les déploiements Skype Entreprise Server déploiements. Vous pouvez modifier la stratégie globale mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont réinitialisées.
    
- **Stratégies de site (facultatives)** Vous pouvez spécifier une ou plusieurs stratégies d’archivage de site, que vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un site spécifique. Une stratégie de site supplante la stratégie globale, mais uniquement pour les sites spécifiés dans les stratégies d’archivage. Vous pouvez modifier ou supprimer les stratégies de site.
    
- **Stratégies utilisateur (facultatives)** Vous pouvez spécifier une ou plusieurs stratégies d’archivage utilisateur, que vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un utilisateur spécifique. Une stratégie utilisateur supplante la stratégie globale et les stratégies de site, mais uniquement pour le ou les utilisateurs auxquels vous attribuez une stratégie utilisateur. Vous pouvez modifier ou supprimer les stratégies utilisateur.
    
> [!NOTE]
> Si vous utilisez l’intégration Exchange pour stocker des données d’archivage dans Microsoft Exchange, les stratégies Exchange 2013 contrôlent l’archivage pour les utilisateurs Exchange 2013. Pour activer l’archivage pour ces utilisateurs, la boîte aux lettres de l’utilisateur doit être placée en In-Place archive. 
  
Pour configurer les paramètres pour une stratégie d’archivage nouvelle ou existante, spécifiez les options suivantes :
- **Nom** Chaque stratégie d’archivage nécessite un nom. Le nom est déterminé par le type de stratégie que vous ajoutez ou modifiez :
    
  - **Stratégie globale** Le nom par défaut est Global. Vous pouvez le remplacer par un nom plus descriptif. Par exemple, Organisation Contoso d’Amérique du Nord.
    
  - **Stratégie de site** Les sites répertoriés dans cette boîte de dialogue incluent tous les sites disponibles dans votre déploiement. Cliquez sur un site individuel pour le sélectionner. Par exemple, Centre de données de Redmond.
    
  - **Stratégie utilisateur** Spécifiez un nom approprié, tel que le nom d’un utilisateur spécifique ou le nom d’un groupe d’utilisateurs ou d’une équipe de votre organisation. Par exemple, Service juridique.
    
- **Description** Cette option est facultative. Utilisez-le pour fournir des détails supplémentaires, tels que l’étendue ou l’utilisation de la stratégie. Par exemple, coordonner avec les services juridiques d’autres sites.
    
- **Archiver les communications internes** Activez cette case à cocher pour activer l’archivage des communications sur votre réseau interne. Par défaut, cette option n’est activée dans aucune stratégie.
    
- **Archiver les communications externes** Activez cette case à cocher pour activer l’archivage des communications qui incluent les utilisateurs externes, tels que les utilisateurs distants (y compris les utilisateurs anonymes et pic), et les partenaires fédérés. Par défaut, cette option n’est activée dans aucune stratégie.
    
Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, notamment l’intégration Exchange, voir Planifier l’archivage dans [Skype Entreprise Server 2015,](../../plan-your-deployment/archiving/archiving.md)Déployer l’archivage pour [Skype Entreprise Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)et Gérer l’archivage dans [Skype Entreprise Server 2015.](../../manage/archiving/archiving.md)

