---
title: Migration des serveurs d’archivage et de surveillance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre environnement Skype entreprise Server 2019 après avoir migré vos pools frontaux. Toutefois, si la fonctionnalité d’archivage et de surveillance est essentielle pour votre organisation, vous devez ajouter l’archivage et la surveillance à votre pool pilote Skype entreprise Server 2019 avant de procéder à la migration afin que la fonctionnalité soit disponible au cours du processus de migration.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752666"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migration des serveurs d’archivage et de surveillance

Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre environnement Skype entreprise Server 2019 après avoir migré vos pools frontaux. Toutefois, si la fonctionnalité d’archivage et de surveillance est essentielle pour votre organisation, vous devez ajouter l’archivage et la surveillance à votre pool pilote Skype entreprise Server 2019 avant de procéder à la migration afin que la fonctionnalité soit disponible au cours du processus de migration. 
  
Si vous voulez la fonctionnalité d’archivage et de surveillance au cours du processus de migration, gardez les considérations suivantes à l’esprit :
  
- Les données d’archivage et les données de surveillance ne sont pas déplacées vers le déploiement de Skype entreprise Server 2019. Les données que vous sauvegardez avant la mise hors service de l’environnement hérité seront votre historique des activités dans l’environnement hérité.
    
- La version héritée du serveur d’archivage et du serveur de surveillance ne peut être associée qu’à un pool frontal hérité. Dans Skype entreprise Server 2019, l’archivage et la surveillance ne sont plus des rôles serveur, mais des services intégrés au pool frontal de Skype entreprise Server 2019.
    
- Pendant la coexistence de vos déploiements hérités et Skype entreprise Server 2019, la version héritée du serveur d’archivage et du serveur de surveillance recueille des données pour les utilisateurs hébergés sur les pools hérités. L’archivage et la surveillance dans Skype entreprise Server 2019 recueillent des données pour les utilisateurs hébergés sur des pools 2019 Skype entreprise Server.
    
    > [!NOTE]
    > Pendant la phase de migration, lorsque vous utilisez toujours votre serveur Edge hérité avec le nouveau pool pilote Skype entreprise Server 2019, la version héritée du serveur d’archivage continue de collecter des données pour les utilisateurs hébergés sur les pools hérités et l’archivage dans Skype entreprise Server 2019 recueille des données pour les utilisateurs hébergés sur des pools Skype entreprise Server 2019. 
  
- Si vous utilisez une solution d’archivage et de surveillance tierce en association avec l’archivage et la surveillance dans Skype entreprise Server 2019, consultez votre fournisseur quand et comment intégrer la solution tierce avec Skype entreprise Server 2019.
    

