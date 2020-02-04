---
title: Expandeur des paramètres du magasin SQL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Pour modifier les propriétés d’une base de données SQL Server, vous devez modifier l’instance de base de données SQL Server. Vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour effectuer des tâches telles que le déplacement de la base de données du serveur d’archivage d’un ordinateur vers un autre. De plus, vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour modifier l’instance de SQL Server qui héberge la Banque centrale de gestion.
ms.openlocfilehash: ccaa6d2ceedfdef3f180de93e763c28b7167d45a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701459"
---
# <a name="sql-store-settings-expander"></a>Expandeur des paramètres du magasin SQL
 
Pour modifier les propriétés d’une base de données SQL Server, vous devez modifier l’instance de base de données SQL Server. Vous ne pouvez pas utiliser la boîte de dialogue **modifier les propriétés** pour effectuer des tâches telles que le déplacement de la base de données du serveur d’archivage d’un ordinateur vers un autre. De plus, vous ne pouvez pas utiliser la boîte de dialogue **modifier les propriétés** pour modifier l’instance de SQL Server qui héberge la Banque centrale de gestion.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Modification des propriétés d’une base de données SQL Server

Pour modifier l’instance de SQL Server qui est utilisée par une autre base de données que la Banque centrale de gestion, procédez comme suit dans générateur de topologie :
  
### <a name="to-modify-an-instance-of-sql-server"></a>Pour modifier une instance de SQL Server

1. Sélectionnez la base de données appropriée sous le nœud **SQL stores** , puis cliquez sur **modifier les propriétés**.
    
2. Dans la boîte de dialogue **modifier les propriétés** , effectuez l’une des opérations suivantes :
    
   - Pour utiliser l’instance SQL Server par défaut, sélectionnez **instance par défaut** , puis cliquez sur **OK**.
    
   - Pour utiliser une instance de base de données nommée, sélectionnez **instance nommée**, entrez le nom de l’instance dans la zone de texte, puis cliquez sur **OK**. Entrez uniquement le nom de l’instance (par exemple, ArchivingInstance), et non le chemin SQL Server complet.
    
Lorsque vous utilisez la boîte de dialogue **modifier les propriétés** , le générateur de topologie ne vérifie pas que l’instance de base de données que vous avez entrée est une instance valide. Par exemple, si vous avez accidentellement typeArchivingInstanec comme nom d’instance, puis cliquez sur **OK**, le générateur de topologie acceptera cette instance non valide. Avant de pouvoir publier cette topologie, vous devez corriger cette erreur : si aucune instance SQL Server n’est disponible, le générateur de topologie ne créera pas cette instance pour vous.
  

