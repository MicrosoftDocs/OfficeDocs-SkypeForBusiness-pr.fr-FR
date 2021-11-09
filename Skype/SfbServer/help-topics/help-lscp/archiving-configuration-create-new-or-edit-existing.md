---
title: 'Configuration de l’archivage : création d’une configuration ou modification d’une configuration existante'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 'Vous utilisez les configurations d’archivage pour contrôler les options d’archivage de votre déploiement. Les configurations d’archivage incluent la configuration globale et éventuellement une ou plusieurs configurations de site ou de pool :'
ms.openlocfilehash: 1de397f6cefb8827e664cfe20bf169151c763049
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838826"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuration de l’archivage : création d’une nouvelle ou modification d’une configuration existante
 
Vous utilisez les configurations d’archivage pour contrôler les options d’archivage de votre déploiement. Les configurations d’archivage incluent la configuration globale et éventuellement une ou plusieurs configurations de site ou de pool :
  
- **Configuration globale** La configuration globale est créée par défaut. Vous pouvez modifier la configuration globale mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont réinitialisées.
    
- **Configuration du site (facultatif)** Vous pouvez spécifier une ou plusieurs configurations d’archivage de site, que vous pouvez configurer pour contrôler les options d’archivage d’un site spécifique. La configuration d’un site remplace la configuration globale, mais uniquement pour les sites spécifiés dans les configurations de site en matière d’archivage. Vous pouvez modifier ou supprimer des configurations de site.
    
- **Configuration du pool (facultatif)** Vous pouvez spécifier une ou plusieurs configurations d’archivage de pool pour contrôler les options d’archivage d’un pool spécifique. Une configuration de pool supplante la configuration globale et la configuration de site, mais seulement pour les pools spécifiés dans les configurations d’archivage de pool. Vous pouvez modifier ou supprimer les configurations de pool.
    
> [!NOTE]
> Les configurations d’archivage s’appliquent aux utilisateurs sur Skype Entreprise Server et, si vous activez l’option d’intégration Microsoft Exchange pour utiliser Exchange 2013 pour stocker les données d’archivage dans Microsoft Exchange, aux utilisateurs d’Exchange 2013. Toutefois, certaines options sont implémentées légèrement différemment pour les utilisateurs Exchange 2013, comme décrit dans la section suivante. 
  
Pour configurer les paramètres pour une configuration d’archivage nouvelle ou existante, spécifiez les options suivantes :
- **Nom** Chaque configuration d’archivage nécessite un nom. Le nom est déterminé par le type de configuration que vous ajoutez ou modifiez :
    
  - **Configuration globale** Le nom par défaut est Global. Par exemple, Organisation Contoso d’Amérique du Nord.
    
  - **Configuration du site** La liste contient les sites disponibles dans votre déploiement. Cliquez sur un site individuel pour le sélectionner. Par exemple, Centre de données de Redmond.
    
  - **Configuration du pool** Spécifiez un nom approprié, qui peut être le nom d’un pool frontal ou d’un serveur Édition Standard spécifique dans votre déploiement. Par exemple, Division Marketing.
    
- **Description** Cette option est facultative. Utilisez-le pour fournir des détails supplémentaires, tels que l’étendue ou l’utilisation de la configuration. Par exemple, coordonner avec les services juridiques d’autres sites.
    
- **Paramètre d’archivage** Les options sont les suivantes :
    
  - **Archiver les sessions de messagerie instantanée**
    
  - **Archiver les sessions de messagerie instantanée et de conférence web**
    
  - **Désactiver l’archivage**
    
- Bloquer les sessions de messagerie instantanée ou de conférence web en cas **d’échec de l’archivage** Les échecs sont les suivants :
    
  - **La défaillance de** la messagerie instantanée A peut être une base de données complète ou un problème avec le service de stockage. Dans ce cas, la messagerie instantanée est bloquée pour les utilisateurs qui ont été activés pour l’archivage.
    
  - **Conférence** Un échec peut être un partage de fichiers indisponible ou un problème avec le service de stockage. Dans ce cas, toutes les conférences actives hébergées dans le pool au moment de l’échec basculent en mode restreint et les nouvelles conférences ne peuvent pas être activées.
    
    La récupération des sessions de messagerie instantanée et de conférence s’effectue automatiquement après la correction des défaillances.
    
- **Intégration Exchange Microsoft** Sélectionnez cette option si vous avez des utilisateurs qui sont Exchange 2013. Avec cette option, Exchange 2013 est utilisé pour stocker les données de ces utilisateurs, si leurs boîtes aux lettres ont été placées en In-Place conserver. Si tous vos utilisateurs sont Exchange 2013, vous n’avez pas besoin de configurer des bases de données SQL Server distinctes pour le stockage des données d’archivage.
    
- **Activer le purge des données d’archivage** Sélectionnez cette option pour activer le purgement et spécifier les options de purge, qui incluent les options suivantes :
    
  - Vidage après un nombre spécifique de jours que vous spécifiez.
    
  - Purge après l’exportation des données d’archivage (qui inclut les données qui ont été téléchargées vers Exchange, si vous activez l’intégration de Microsoft Exchange).
    
    > [!NOTE]
    > Si vous activez l’intégration de Microsoft Exchange, la purge pour les utilisateurs Exchange 2013 et dont les boîtes aux lettres sont placées en In-Place est contrôlée par Exchange. La seule exception concerne les fichiers de conférence, qui sont stockés sur le partage de fichiers Lync Server. Ces fichiers sont vidés du partage de fichiers une fois seulement que les fichiers ont été exportés (téléchargés vers Exchange) si vous sélectionnez l’option consistant à vider les données après l’exportation des données d’archivage, ou après le nombre maximal de jours spécifié si vous spécifiez un nombre maximal de jours de rétention. 
  
Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, notamment l’intégration Exchange, voir Planifier l’archivage dans [Skype Entreprise Server 2015,](../../plan-your-deployment/archiving/archiving.md)Déployer l’archivage pour [Skype Entreprise Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)et Gérer l’archivage dans [Skype Entreprise Server 2015.](../../manage/archiving/archiving.md)

