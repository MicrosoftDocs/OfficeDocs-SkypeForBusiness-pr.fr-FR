---
title: Configuration de l’archivage création d’un nouveau ou modification existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous utilisez des configurations d’archivage pour contrôler les options d’archivage de votre déploiement. Les configurations d’archivage incluent la configuration globale et, éventuellement, une ou plusieurs configurations de site ou de pool :'
ms.openlocfilehash: 0c387095f40078246a1391af5968925a7b28caf2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691139"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuration de l’archivage : création d’un archivage ou modification d’un archivage existant
 
Vous utilisez des configurations d’archivage pour contrôler les options d’archivage de votre déploiement. Les configurations d’archivage incluent la configuration globale et, éventuellement, une ou plusieurs configurations de site ou de pool :
  
- **Configuration globale** La configuration globale est créée par défaut. Vous pouvez modifier la configuration globale, mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, les valeurs par défaut de toutes les options sont restaurées.
    
- **Configuration du site (facultatif)** Vous pouvez spécifier une ou plusieurs configurations d’archivage de site, qui peuvent chacune être configurées pour contrôler les options d’archivage d’un site spécifique. La configuration d’un site remplace la configuration globale, mais uniquement pour les sites spécifiés dans les configurations de site en matière d’archivage. Vous pouvez modifier ou supprimer les configurations de site.
    
- **Configuration du pool (facultatif)** Vous pouvez spécifier une ou plusieurs configurations d’archivage du pool pour contrôler les options d’archivage d’un pool spécifique. Une configuration de pool remplace la configuration globale et la configuration de site, mais seulement pour les pools spécifiés dans les configurations d’archivage de pool. Vous pouvez modifier ou supprimer les configurations de pool.
    
> [!NOTE]
> La configuration de l’archivage s’applique aux utilisateurs hébergés sur Skype entreprise Server et, si vous activez l’option d’intégration de Microsoft Exchange pour stocker les données d’archivage dans Microsoft Exchange, aux utilisateurs hébergés sur Exchange. Toutefois, certaines options sont implémentées légèrement différemment pour les utilisateurs hébergés sur Exchange, comme décrit dans la section suivante. 
  
Pour configurer les paramètres pour une configuration d’archivage nouvelle ou existante, spécifiez les options suivantes :
- **Nom** Chaque configuration de l’archivage nécessite un nom. Le nom est déterminé par le type de configuration que vous ajoutez ou modifiez :
    
  - **Configuration globale** Le nom par défaut est global. Par exemple, « Organisation Contoso d’Amérique du Nord".
    
  - **Configuration du site** La liste contient les sites disponibles dans votre déploiement. Cliquez sur un site individuel pour le sélectionner. Par exemple, Centre de données de Redmond.
    
  - **Configuration du pool** Spécifiez un nom approprié, qui peut correspondre au nom d’un pool frontal spécifique ou d’un serveur Standard Edition dans votre déploiement. Par exemple, « Division Marketing ».
    
- **Description** Facultatif. Vous pouvez l’utiliser pour fournir des informations supplémentaires, telles que la portée ou l’utilisation de la configuration. Par exemple, la coordination avec les services juridiques d’autres sites.
    
- **Paramètre d’archivage** Les options disponibles sont les suivantes :
    
  - **Archiver les sessions de messagerie instantanée**
    
  - **Archiver les sessions de messagerie instantanée et de conférence web**
    
  - **Désactiver l’archivage**
    
- **Bloquer des sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage** Les échecs incluent les éléments suivants :
    
  - **Message instantané** un échec peut s’agir d’une base de données complète ou d’un problème lié au service de stockage. Dans ce cas, la messagerie instantanée est bloquée pour les utilisateurs activés pour l’archivage.
    
  - **Conférences** téléphoniques Un échec peut être un partage de fichier non disponible ou un problème avec le service de stockage. Dans ce cas, toutes les conférences actives hébergées dans le pool au moment de la défaillance passent en mode restreint et l’activation de nouvelles conférences est suspendue.
    
    La récupération des sessions de messagerie instantanée et de conférence s’effectue automatiquement après la correction des défaillances.
    
- **Intégration de Microsoft Exchange** Sélectionnez cette option si vous avez des utilisateurs hébergés sur Exchange. Avec cette option, Exchange est utilisé pour stocker les données de ces utilisateurs, si leurs boîtes aux lettres ont été placées sur le blocage sur place. Si tous vos utilisateurs sont hébergés sur Exchange, vous n’avez pas besoin de configurer des bases de données SQL Server distinctes pour le stockage des données d’archivage.
    
- **Activer la suppression définitive des données d’archivage** Sélectionnez cette option pour activer la purge et spécifier les options de purge, qui incluent les éléments suivants :
    
  - Vidage après un nombre spécifique de jours que vous spécifiez.
    
  - Vider après l’exportation des données d’archivage (y compris les données téléchargées vers Exchange, si vous activez l’intégration de Microsoft Exchange).
    
    > [!NOTE]
    > Si vous activez l’intégration de Microsoft Exchange, le vidage pour les utilisateurs hébergés sur Exchange et leurs boîtes aux lettres placés dans la conservation inaltérable sont contrôlés par Exchange. La seule exception est pour les fichiers de conférence qui sont stockés sur le partage de fichiers de Lync Server. Ces fichiers ne sont purgés à partir du partage de fichiers qu’une fois que les fichiers ont été exportés (téléchargés vers Exchange) si vous sélectionnez l’option de purge des données après l’exportation des données d’archivage ou après le nombre maximal de jours spécifié si vous spécifiez un nombre maximal de jours de rétention. 
  
Pour plus d’informations sur la fonctionnalité d’archivage et les fonctionnalités, notamment l’intégration d’Exchange, reportez-vous à la rubrique [planification de l’archivage dans Skype entreprise Server](../../../plan-your-deployment/archiving/archiving.md), [déploiement de l’archivage pour Skype entreprise Server](../../../deploy/deploy-archiving/deploy-archiving.md)et [gestion de l’archivage dans Skype entreprise Server](../../../manage/archiving/archiving.md).

