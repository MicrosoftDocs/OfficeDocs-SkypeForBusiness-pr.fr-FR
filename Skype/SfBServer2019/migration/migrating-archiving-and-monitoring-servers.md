---
title: Migration des serveurs d’archivage et de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre Skype pour Business Server 2019 environnement après avoir fait migrer vos pools frontaux. Toutefois, si l’archivage et la fonctionnalité d’analyse sont critiques pour votre organisation, vous devez ajouter l’archivage et d’analyse à votre Skype pour le pool pilote Business Server 2019 avant de migrer afin que la fonctionnalité est disponible pendant le processus de migration.
ms.openlocfilehash: 24dc3e3007fd9a58c23f9c15a31cccc766d45e83
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896091"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migration des serveurs d’archivage et de surveillance

Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre Skype pour Business Server 2019 environnement après avoir fait migrer vos pools frontaux. Toutefois, si l’archivage et la fonctionnalité d’analyse sont critiques pour votre organisation, vous devez ajouter l’archivage et d’analyse à votre Skype pour le pool pilote Business Server 2019 avant de migrer afin que la fonctionnalité est disponible pendant le processus de migration. 
  
Si vous souhaitez que les fonctionnalités d’archivage et de surveillance au cours du processus de migration, gardez les points suivants à l’esprit :
  
- Données d’archivage et de données de surveillance ne sont pas déplacés vers le Skype pour le déploiement de Business Server 2019. Les données à que sauvegarder avant de désactiver l’ancien environnement sera votre historique des activités dans l’ancien environnement.
    
- La version héritée de serveur d’archivage et le serveur de surveillance peut être associée qu’avec un pool frontal hérité. Dans Skype pour Business Server 2019, d’archivage et de surveillance ne sont plus rôles de serveur, mais les services intégrés le Skype pour Business Server 2019 un pool frontal.
    
- Lors de la période que votre hérité et Skype pour les déploiements Business Server 2019 coexistent, la version héritée de serveur d’archivage et le serveur de surveillance recueillir des données pour les utilisateurs hébergés sur les pools hérités. Archivage et surveillance dans Skype pour Business Server 2019 rassembler des données pour les utilisateurs hébergement sur Skype pour les pools d’entreprise Server 2019.
    
    > [!NOTE]
    > Pendant la phase de migration lorsque vous avez toujours à l’aide de votre serveur Edge hérité avec le nouveau Skype pour Business Server 2019 pool pilote, la version héritée de serveur d’archivage continue à recueillir des données pour les utilisateurs hébergé sur les pools hérités et archivage dans Skype pour les entreprises Serveur 2019 recueille des données pour les utilisateurs hébergement sur Skype pour les pools d’entreprise Server 2019. 
  
- Si vous utilisez un tiers à l’archivage et surveillance solution conjointement avec archivage et de surveillance dans Skype pour Business Server 2019, consultez votre fournisseur quand et comment vous souhaitez intégrer la solution tierce avec Skype pour Business Server 2019.
    

