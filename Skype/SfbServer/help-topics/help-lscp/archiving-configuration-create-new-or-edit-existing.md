---
title: Configuration d’archivage, créer ou modifier une existante
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 'Vous utilisez des configurations d’archivage pour contrôler les options d’archivage de votre déploiement. Les configurations d’archivage incluent la configuration globale et, éventuellement, une ou plusieurs configurations de site ou de pool :'
ms.openlocfilehash: 49227ded326c893d42852796e9c783a2dc4096cd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuration de l’archivage : création d’un archivage ou modification d’un archivage existant
 
Vous utilisez des configurations d’archivage pour contrôler les options d’archivage de votre déploiement. Les configurations d’archivage incluent la configuration globale et, éventuellement, une ou plusieurs configurations de site ou de pool :
  
- **Configuration globale** La configuration globale est créée par défaut. Vous pouvez modifier la configuration globale, mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.
    
- **Configuration du site (facultative)** Vous pouvez spécifier une ou plusieurs site d’archivage configurations, que chacun d'entre eux vous pouvez configurer pour contrôler les options pour un site spécifique d’archivage. La configuration d’un site remplace la configuration globale, mais uniquement pour les sites spécifiés dans les configurations de site en matière d’archivage. Vous pouvez modifier ou supprimer les configurations de site.
    
- **Configuration de pool (facultatif)** Vous pouvez spécifier une ou plusieurs pool d’archivage configurations, au contrôle de l’archivage des options pour un pool spécifique. Une configuration de pool remplace la configuration globale et la configuration de site, mais seulement pour les pools spécifiés dans les configurations d’archivage de pool. Vous pouvez modifier ou supprimer les configurations de pool.
    
> [!NOTE]
> Appliquent des configurations d’archivage pour les utilisateurs hébergés sur Skype pour le serveur de l’entreprise et, si vous activez l’option d’intégration de Microsoft Exchange à utiliser Exchange 2013 pour stocker les données d’archivage dans Microsoft Exchange, pour les utilisateurs hébergés sur Exchange 2013. Toutefois, certaines options sont implémentées légèrement différemment pour les utilisateurs hébergés sur Exchange 2013, comme décrit dans la section suivante. 
  
Pour configurer les paramètres pour une configuration d’archivage nouvelle ou existante, spécifiez les options suivantes :
- **Nom** Chaque configuration d’archivage requiert un nom. Le nom est déterminé par le type de configuration que vous ajoutez ou modifiez :
    
  - **Configuration globale** Le nom par défaut est Global. Par exemple, « Organisation Contoso d’Amérique du Nord ».
    
  - **Configuration de site** La liste contient les sites disponibles dans votre déploiement. Cliquez sur un site individuel pour le sélectionner. Par exemple, Centre de données de Redmond.
    
  - **Configuration de pool** Spécifiez un nom approprié, ce qui peut être le nom d’un pool frontal spécifique ou le serveur Standard Edition Server dans votre déploiement. Par exemple, « Division Marketing ».
    
- **Description** Cette option est facultative. Elle permet de fournir des détails supplémentaires, tels que l’étendue ou l’utilisation de la configuration. Par exemple, coordonner avec les services juridiques des autres Sites.
    
- **Paramètres d’archivage** Contient les options suivantes :
    
  - **Archiver les sessions de messagerie instantanée**
    
  - **Archiver les sessions de messagerie instantanée et de conférence web**
    
  - **Désactiver l’archivage**
    
- **Les sessions de conférence web si l’échec de l’archivage ou de bloquer la messagerie instantanée (MI)** Échecs sont les suivants :
    
  - **Messagerie instantanée** un échec peut être un problème avec le service de stockage ou base de données complète. Dans ce cas, la messagerie instantanée est bloquée pour les utilisateurs activés pour l’archivage.
    
  - **Conférence** Un échec peut être un partage de fichier non disponible ou un problème avec le service de stockage. Dans ce cas, toutes les conférences actives hébergées dans le pool lors de l’échec passent en mode restreint, et l’activation de nouvelles conférences est suspendue.
    
    La récupération des sessions de messagerie instantanée et de conférence est effectué automatiquement après la correction des échecs.
    
- **Intégration de Microsoft Exchange** Sélectionnez cette option si vous avez des utilisateurs qui sont hébergés sur Exchange 2013. Avec cette option, Exchange 2013 est utilisé pour stocker des données pour les utilisateurs, si leurs boîtes aux lettres ont été placés sur Place maintenez. Si tous vos utilisateurs sont hébergés sur Exchange 2013, vous n’avez pas besoin configurer les bases de données distinctes de SQL Server pour le stockage de l’archivage des données.
    
- **Activer la purge de données d’archivage** Sélectionnez cette option pour activer la purge et spécifier des options de purge, qui incluent les éléments suivants :
    
  - Vidage après un nombre spécifique de jours que vous spécifiez.
    
  - Purge d’après les données d’archivage a été exporté (ce qui inclut les données qui ont été téléchargées vers Exchange, si vous activez l’intégration de Microsoft Exchange).
    
    > [!NOTE]
    > Si vous activez l’intégration de Microsoft Exchange, pour les utilisateurs hébergés sur Exchange 2013 et la purge avec leurs boîtes aux lettres placées sur Place maintenez est contrôlé par Exchange. La seule exception concerne les fichiers de conférence, qui sont stockés sur le partage de fichiers de Lync Server. Ces fichiers ne sont purgés à partir du partage de fichiers qu’une fois que les fichiers ont été exportés (téléchargés vers Exchange) si vous sélectionnez l’option de purge des données après l’exportation des données d’archivage ou après le nombre maximal de jours spécifié si vous spécifiez un nombre maximal de jours de rétention. 
  
Pour plus d’informations sur la fonctionnalité d’archivage et de fonctionnalités, y compris l’intégration d’Exchange, consultez [planification d’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [déployer l’archivage pour Skype pour Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)et [gérer l’archivage dans Skype pour Entreprise 2015 de serveur](../../manage/archiving/archiving.md).

