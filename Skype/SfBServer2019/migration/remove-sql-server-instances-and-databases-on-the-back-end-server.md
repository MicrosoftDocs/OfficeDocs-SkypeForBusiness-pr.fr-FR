---
title: Suppression des instances et des bases de données SQL Server sur le serveur principal
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
description: Vous supprimez les bases de données et les instances Microsoft SQL Server après avoir supprimé les serveurs en cours d’exécution qui en dépendent, ou après avoir reconfiguré les serveurs pour qu’ils utilisent une autre base de données. Vous devez effectuer la procédure décrite dans cette rubrique lorsque vous désactivez le serveur SQL Server actuel ou reconfigurez le serveur actuel de telle sorte qu’il rende les bases de données obsolètes ou indisponibles.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752156"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Suppression des instances et des bases de données SQL Server sur le serveur principal

Vous supprimez les bases de données et les instances Microsoft SQL Server après avoir supprimé les serveurs en cours d’exécution qui en dépendent, ou après avoir reconfiguré les serveurs pour qu’ils utilisent une autre base de données. Vous devez effectuer la procédure décrite dans cette rubrique lorsque vous désactivez le serveur SQL Server actuel ou reconfigurez le serveur actuel de telle sorte qu’il rende les bases de données obsolètes ou indisponibles.
  
Pour supprimer les bases de données ou les instances du serveur d’archivage ou du serveur de surveillance, vous devez d’abord supprimer le rôle serveur. De même, pour supprimer les instances ou les bases de données du pool frontal, vous devez d’abord supprimer ou reconfigurer le rôle de serveur dépendant. Ces procédures ne font pas de distinction entre les bases de données colocalisées et les instances séparées des serveurs. Elles ne sont pas affectées par la colocalisation des bases de données.
  
## <a name="in-this-section"></a>Dans cette section

- [Suppression de la base de données SQL Server pour un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Suppression de la base de données SQL Server pour un serveur de surveillance](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Suppression de la base de données SQL Server pour un serveur d’archivage](remove-the-sql-server-database-for-an-archiving-server.md)
    

