---
title: Supprimer des instances de SQL Server et les bases de données sur le serveur principal
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Pour supprimer les bases de données Microsoft SQL Server, instances après avoir supprimé les serveurs exécutant qui dépendent les, ou une fois que vous reconfigurez les serveurs pour utiliser une autre base de données. Vous devez effectuer la procédure dans cette rubrique lorsque vous retirer le serveur SQL Server en cours ou reconfigurez le serveur actuel de telle sorte qu’il s’affiche les bases de données obsolètes ou non disponible.
ms.openlocfilehash: 648c808ee293c4fa33352d0f68ba337e4a489d27
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027878"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Supprimer des instances de SQL Server et les bases de données sur le serveur principal

Pour supprimer les bases de données Microsoft SQL Server, instances après avoir supprimé les serveurs exécutant qui dépendent les, ou une fois que vous reconfigurez les serveurs pour utiliser une autre base de données. Vous devez effectuer la procédure dans cette rubrique lorsque vous retirer le serveur SQL Server en cours ou reconfigurez le serveur actuel de telle sorte qu’il s’affiche les bases de données obsolètes ou non disponible.
  
Pour supprimer les bases de données ou les instances de serveur d’archivage ou un serveur de surveillance, vous devez d’abord supprimer le rôle de serveur. De même, pour supprimer les instances de bases de données pour un pool frontal, vous devez tout d’abord supprimer ou reconfigurer le rôle de serveur qui en dépendent. Ces procédures font pas de distinction entre les bases de données COLOCALISÉES ou instances distinctes pour les serveurs. Les procédures ne sont pas affectés par la colocalisation des bases de données.
  
## <a name="in-this-section"></a>Contenu de cette section

- [Supprimer la base de données SQL Server pour un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Supprimer la base de données SQL Server pour un serveur de surveillance](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Supprimer la base de données SQL Server pour un serveur d’archivage](remove-the-sql-server-database-for-an-archiving-server.md)
    

