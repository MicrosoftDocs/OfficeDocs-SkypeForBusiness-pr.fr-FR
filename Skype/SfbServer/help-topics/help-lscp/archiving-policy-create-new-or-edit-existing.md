---
title: Stratégie d’archivage création d’un nouveau ou modification existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Les stratégies d’archivage permettent de contrôler l’archivage des communications internes et externes dans votre déploiement pour les utilisateurs qui sont hébergés sur Skype entreprise Server. Les stratégies d’archivage incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies de site et utilisateur :'
ms.openlocfilehash: e37d4365af0c817d49d4314987ee41392a0d80cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823197"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Stratégie d’archivage : création d’une stratégie ou modifier d’une stratégie existante
 
Les stratégies d’archivage permettent de contrôler l’archivage des communications internes et externes dans votre déploiement pour les utilisateurs qui sont hébergés sur Skype entreprise Server. Les stratégies d’archivage incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies de site et utilisateur :
  
- **Politique globale** La politique globale est créée par défaut dans tous les déploiements de Skype entreprise Server. Vous pouvez modifier la stratégie globale, mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.
    
- **Stratégies de site (facultatif)** Vous pouvez spécifier une ou plusieurs stratégies d’archivage de site que vous pouvez configurer pour activer et désactiver l’archivage des communications internes ou externes pour un site spécifique. Une stratégie de site remplace la stratégie globale, mais uniquement pour les sites spécifiés dans les stratégies d’archivage. Vous pouvez modifier ou supprimer les stratégies de site.
    
- **Stratégies utilisateur (facultatif)** Vous pouvez spécifier une ou plusieurs stratégies d’archivage des utilisateurs, qui peuvent être configurées pour activer et désactiver l’archivage pour des communications internes ou externes pour un utilisateur spécifique. Une stratégie utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour le ou les utilisateurs auxquels vous attribuez une stratégie utilisateur. Vous pouvez modifier ou supprimer les stratégies utilisateur.
    
> [!NOTE]
> Si vous utilisez l’intégration Exchange pour stocker les données d’archivage dans Microsoft Exchange, puis que les stratégies Exchange 2013 contrôlent l’archivage pour les utilisateurs hébergés sur Exchange 2013. Pour activer l’archivage de ces utilisateurs, la boîte aux lettres de l’utilisateur doit être placée sur une conservation inaltérable. 
  
Pour configurer les paramètres pour une stratégie d’archivage nouvelle ou existante, spécifiez les options suivantes :
- **Nom** Chaque stratégie d’archivage nécessite un nom. Le nom est déterminé par le type de stratégie que vous ajoutez ou modifiez :
    
  - **Politique globale** Le nom par défaut est global. Vous pouvez le remplacer par un nom plus descriptif. Par exemple, « Organisation Contoso d’Amérique du Nord".
    
  - **Stratégie de site** Les sites répertoriés dans cette boîte de dialogue incluent tous les sites disponibles dans votre déploiement. Cliquez sur un site individuel pour le sélectionner. Par exemple, Centre de données de Redmond.
    
  - **Stratégie** de l’utilisateur Spécifiez un nom approprié, tel que le nom d’un utilisateur spécifique ou le nom d’un groupe d’utilisateurs ou d’une équipe au sein de votre organisation. Par exemple, Service juridique.
    
- **Description** Facultatif. Vous pouvez l’utiliser pour fournir des informations supplémentaires, telles que la portée ou l’utilisation de la stratégie. Par exemple, la coordination avec les services juridiques d’autres sites.
    
- **Archiver des communications internes** Activez cette case à cocher pour activer l’archivage des communications sur votre réseau interne. Par défaut, cette option n’est activée dans aucune stratégie.
    
- **Archiver des communications externes** Activez cette case à cocher pour activer l’archivage des communications qui incluent des utilisateurs externes, tels que des utilisateurs distants (y compris les utilisateurs anonymes et de configuration PIC) et des partenaires fédérés. Par défaut, cette option n’est activée dans aucune stratégie.
    
Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, notamment l’intégration d’Exchange, voir [planification de l’archivage dans Skype entreprise server 2015](../../plan-your-deployment/archiving/archiving.md), déploiement de l’archivage [pour skype entreprise Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)et [gestion de l’archivage dans Skype entreprise Server 2015](../../manage/archiving/archiving.md).

