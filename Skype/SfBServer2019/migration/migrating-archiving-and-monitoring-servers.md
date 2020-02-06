---
title: Migration des serveurs d’archivage et de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si vous avez déployé le serveur d’archivage et surveillé votre serveur dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre environnement 2019 Skype entreprise Server après la migration de vos pools front-end. En revanche, si la fonctionnalité d’archivage et de surveillance est essentielle pour votre organisation, il est conseillé d’ajouter l’archivage et la surveillance à votre liste de pilotes de pilotes 2019 Skype entreprise Server avant de procéder à la migration de manière à ce que la fonctionnalité soit disponible pendant le processus de migration.
ms.openlocfilehash: 5088f4b4f72ddc083cf2868df893946561eb2469
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813452"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migration des serveurs d’archivage et de surveillance

Si vous avez déployé le serveur d’archivage et surveillé votre serveur dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre environnement 2019 Skype entreprise Server après la migration de vos pools front-end. En revanche, si la fonctionnalité d’archivage et de surveillance est essentielle pour votre organisation, il est conseillé d’ajouter l’archivage et la surveillance à votre liste de pilotes de pilotes 2019 Skype entreprise Server avant de procéder à la migration de manière à ce que la fonctionnalité soit disponible pendant le processus de migration. 
  
Si vous voulez utiliser les fonctionnalités d’archivage et de surveillance pendant le processus de migration, tenez compte des points suivants :
  
- Les données d’archivage et de surveillance ne sont pas déplacées vers le déploiement 2019 de Skype entreprise Server. Les données que vous sauvegardez avant de désactiver l’environnement hérité seront votre historique d’activités dans l’environnement hérité.
    
- La version héritée du serveur d’archivage et de la surveillance du serveur peut être associée uniquement à un pool frontal hérité. Dans Skype entreprise Server 2019, l’archivage et la surveillance ne constituent plus de rôles de serveur, mais les services intégrés au pool frontal 2019 de Skype entreprise Server.
    
- Pendant la période de coexistence de vos déploiements d’anciens et de Skype entreprise Server 2019, la version héritée du serveur d’archivage et la surveillance du serveur collectent des données pour les utilisateurs hébergés sur des pools hérités. Archivage et surveillance dans Skype entreprise Server 2019 rassemblez les données des utilisateurs hébergés sur les pools 2019 de Skype entreprise Server.
    
    > [!NOTE]
    > Pendant la phase de migration lorsque vous utilisez toujours votre serveur de bord traditionnel avec le nouveau Skype entreprise Server 2019, la version héritée du serveur d’archivage continue de rassembler les données pour les utilisateurs hébergés sur des listes héritées et l’archivage dans Skype entreprise. Server 2019 recueille des données pour les utilisateurs hébergés sur des pools 2019 de Skype entreprise Server. 
  
- Si vous utilisez une solution tierce d’archivage et de surveillance conjointement avec l’archivage et la surveillance dans Skype entreprise Server 2019, contactez votre revendeur pour savoir quand et comment vous devez intégrer la solution tierce dans Skype entreprise Server 2019.
    

