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
ms.localizationpriority: medium
description: Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre environnement Skype Entreprise Server 2019 après avoir migré vos pools frontux. Toutefois, si les fonctionnalités d’archivage et de surveillance sont essentielles pour votre organisation, vous devez ajouter l’archivage et la surveillance à votre pool pilote Skype Entreprise Server 2019 avant de migrer afin que la fonctionnalité soit disponible pendant le processus de migration.
ms.openlocfilehash: a5b839a1eb7d460a57d6adf36901c50479f203ad
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596168"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migration des serveurs d’archivage et de surveillance

Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre environnement Skype Entreprise Server 2019 après avoir migré vos pools frontux. Toutefois, si les fonctionnalités d’archivage et de surveillance sont essentielles pour votre organisation, vous devez ajouter l’archivage et la surveillance à votre pool pilote Skype Entreprise Server 2019 avant de migrer afin que la fonctionnalité soit disponible pendant le processus de migration. 
  
Si vous voulez la fonctionnalité d’archivage et de surveillance au cours du processus de migration, gardez les considérations suivantes à l’esprit :
  
- Les données d’archivage et de surveillance ne sont pas déplacées vers le déploiement Skype Entreprise Server 2019. Les données que vous back up avant de désaffecter l’environnement hérité seront votre historique d’activité dans l’environnement hérité.
    
- La version héritée du serveur d’archivage et du serveur de surveillance peut être associée uniquement à un pool frontal hérité. Dans Skype Entreprise Server 2019, l’archivage et la surveillance ne sont plus des rôles serveur, mais des services intégrés au pool frontal Skype Entreprise Server 2019.
    
- Pendant la coexistence de vos déploiements hérités et Skype Entreprise Server 2019, la version héritée du serveur d’archivage et du serveur de surveillance recueille des données pour les utilisateurs qui sont sur des pools hérités. L’archivage et la surveillance dans Skype Entreprise Server 2019 collectent des données pour les utilisateurs Skype Entreprise Server pools 2019.
    
    > [!NOTE]
    > Au cours de la phase de migration, lorsque vous utilisez toujours votre serveur Edge hérité avec le nouveau pool pilote Skype Entreprise Server 2019, la version héritée du serveur d’archivage continue de collecter des données pour les utilisateurs d’accueil sur les pools hérités et l’archivage dans Skype Entreprise Server 2019 collecte les données pour les utilisateurs qui sont homed sur des pools Skype Entreprise Server 2019. 
  
- Si vous utilisez une solution d’archivage et de surveillance tierce conjointement avec l’archivage et la surveillance dans Skype Entreprise Server 2019, consultez votre fournisseur pour savoir quand et comment intégrer la solution tierce à Skype Entreprise Server 2019.
    

