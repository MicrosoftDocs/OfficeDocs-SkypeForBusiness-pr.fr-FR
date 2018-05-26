---
title: Configuration d’archivage créer une nouvelle ou en modifier une existant
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
ms.openlocfilehash: 93bddc8bbba3280ae4e40c0031e65acc6965aa72
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2018
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuration de l’archivage : création d’un archivage ou modification d’un archivage existant
 
Vous utilisez des configurations d’archivage pour contrôler les options d’archivage de votre déploiement. Les configurations d’archivage incluent la configuration globale et, éventuellement, une ou plusieurs configurations de site ou de pool :
  
- **Configuration globale** La configuration globale créée par défaut. Vous pouvez modifier la configuration globale, mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.
    
- **Configuration du site (facultative)** Vous pouvez spécifier une ou plusieurs sites d’archivage configurations, que chacun d'entre eux vous pouvez configurer pour contrôler l’archivage des options pour un site spécifique. La configuration d’un site remplace la configuration globale, mais uniquement pour les sites spécifiés dans les configurations de site en matière d’archivage. Vous pouvez modifier ou supprimer les configurations de site.
    
- **Configuration du pool (facultative)** Vous pouvez spécifier un ou plusieurs pool configurations d’archivage, au contrôle options d’archivage d’un pool spécifique. Une configuration de pool remplace la configuration globale et la configuration de site, mais seulement pour les pools spécifiés dans les configurations d’archivage de pool. Vous pouvez modifier ou supprimer les configurations de pool.
    
> [!NOTE]
> Les configurations d’archivage s’appliquent aux utilisateurs hébergés sur Skype pour Business Server et, si vous activez l’option d’intégration de Microsoft Exchange à utiliser Exchange 2013 pour stocker des données d’archivage dans Microsoft Exchange, les utilisateurs hébergés sur Exchange 2013. Cependant, certaines options sont implémentées différemment pour les utilisateurs hébergés sur Exchange 2013, comme décrit dans la section suivante. 
  
Pour configurer les paramètres pour une configuration d’archivage nouvelle ou existante, spécifiez les options suivantes :
- **Nom** Chaque configuration d’archivage requiert un nom. Le nom est déterminé par le type de configuration que vous ajoutez ou modifiez :
    
  - **Configuration globale** Le nom par défaut est Global. Par exemple, « Organisation Contoso d’Amérique du Nord ».
    
  - **Configuration de site** La liste contient les sites disponibles dans votre déploiement. Cliquez sur un site individuel pour le sélectionner. Par exemple, Centre de données de Redmond.
    
  - **Configuration du pool** Spécifiez un nom approprié, qui peut être le nom d’un pool frontal spécifique ou le serveur Standard Edition Server dans votre déploiement. Par exemple, « Division Marketing ».
    
- **Description** Cette étape est facultative. Utilisez-le pour fournir des détails supplémentaires, tels que l’étendue ou l’utilisation de la configuration. Par exemple, coordonner avec les services juridiques des autres Sites.
    
- **Paramètre d’archivage** Les options sont les suivantes :
    
  - **Archiver les sessions de messagerie instantanée**
    
  - **Archiver les sessions de messagerie instantanée et de conférence web**
    
  - **Désactiver l’archivage**
    
- **Bloquer la messagerie instantanée (MI) ou des sessions de conférence web si l’échec de l’archivage** Échecs sont les suivantes :
    
  - **Messagerie instantanée** un échec peut être une base de données complète ou d’un problème avec le service de stockage. Dans ce cas, la messagerie instantanée est bloquée pour les utilisateurs activés pour l’archivage.
    
  - **Conférence** Une défaillance peut être un partage de fichier non disponible ou un problème avec le service de stockage. Dans ce cas, toutes les conférences actives hébergées dans le pool lors de l’échec passent en mode restreint, et l’activation de nouvelles conférences est suspendue.
    
    La récupération des sessions de messagerie instantanée et de conférence est effectué automatiquement après la correction des échecs.
    
- **Intégration à Microsoft Exchange** Sélectionnez cette option si vous avez des utilisateurs qui sont hébergés sur Exchange 2013. Cette option, Exchange 2013 est utilisé pour stocker les données pour les utilisateurs, si leurs boîtes aux lettres ont été mis en blocage sur Place. Si tous vos utilisateurs sont hébergés sur Exchange 2013, il est inutile définir des bases de données SQL Server distincts pour le stockage des données d’archivage.
    
- **Activer le vidage des données d’archivage** Sélectionnez cette option pour activer le vidage et spécifier les options de vidage, notamment les suivants :
    
  - Vidage après un nombre spécifique de jours que vous spécifiez.
    
  - Vidage après les données d’archivage a été exporté (qui inclut les données qui a été téléchargées vers Exchange, si vous activez l’intégration de Microsoft Exchange).
    
    > [!NOTE]
    > Si vous activez l’intégration de Microsoft Exchange, le vidage pour les utilisateurs hébergés sur Exchange 2013 et avec leurs boîtes aux lettres placées en blocage sur Place est contrôlé par Exchange. La seule exception est pour les fichiers de conférence, qui sont stockés sur le partage de fichiers Lync Server. Ces fichiers ne sont purgés à partir du partage de fichiers qu’une fois que les fichiers ont été exportés (téléchargés vers Exchange) si vous sélectionnez l’option de purge des données après l’exportation des données d’archivage ou après le nombre maximal de jours spécifié si vous spécifiez un nombre maximal de jours de rétention. 
  
Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, y compris l’intégration d’Exchange, voir [planifier l’archivage dans Skype pour Business Server 2015](../../../plan-your-deployment/archiving/archiving.md), [déployer l’archivage pour Skype pour Business Server 2015](../../../deploy/deploy-archiving/deploy-archiving.md)et [gérer l’archivage dans Skype pour Entreprise 2015 Server](../../../manage/archiving/archiving.md).

