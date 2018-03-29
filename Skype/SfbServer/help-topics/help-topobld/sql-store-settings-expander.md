---
title: Développement de paramètres SQL magasin
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Pour modifier les propriétés d’une base de données SQL Server, vous devez modifier l’instance de base de données SQL Server. Vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour effectuer des tâches telles que le déplacement de votre base de données du serveur d’archivage à partir d’un ordinateur à un autre. En outre, vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour modifier l’instance de SQL Server qui héberge le magasin Central de gestion.
ms.openlocfilehash: 2a1fc051e3dc848272a7cad539eaa749ff95d9b9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="sql-store-settings-expander"></a>Développement de paramètres SQL magasin
 
Pour modifier les propriétés d’une base de données SQL Server, vous devez modifier l’instance de base de données SQL Server. Vous ne pouvez pas utiliser la boîte de dialogue **Modifier les propriétés** pour effectuer des tâches telles que le déplacement de votre base de données du serveur d’archivage à partir d’un ordinateur à un autre. En outre, vous ne pouvez pas utiliser la boîte de dialogue **Modifier les propriétés** pour modifier l’instance de SQL Server qui héberge le magasin Central de gestion.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Modification des propriétés d’une base de données de SQL Server

Pour modifier l’instance de SQL Server qui est utilisé par une base de données autre que le magasin Central de gestion, procédez comme suit dans le Générateur de topologie :
  
### <a name="to-modify-an-instance-of-sql-server"></a>Pour modifier une instance de SQL Server

1. Sélectionnez la base de données appropriée, sous le nœud **stocke de SQL** , puis cliquez sur **Modifier les propriétés**.
    
2. Dans la boîte de dialogue **Modifier les propriétés** , effectuez l’une des opérations suivantes :
    
  - Pour utiliser l’instance de SQL Server par défaut, sélectionnez **l’Instance par défaut** et puis cliquez sur **OK**.
    
  - Pour utiliser une instance nommée de la base de données, sélectionnez **Instance nommée**, entrez le nom de l’instance dans la zone de texte, puis cliquez sur **OK**. Vous devez entrer uniquement le nom de l’instance (par exemple, ArchivingInstance) et pas le chemin entier de SQL Server.
    
Lorsque vous travaillez dans la boîte de dialogue **Modifier les propriétés** , le Générateur de topologies ne vérifiera pas que l’instance de base de données que vous avez entré est une instance valide. Par exemple, si vous par inadvertance typeArchivingInstanec comme nom d’instance et puis cliquez sur **OK**, le Générateur de topologies acceptera cette instance non valide. Avant de pouvoir publier cette topologie, vous devez corriger cette erreur : si une instance de SQL Server ne peut pas être trouvée, le Générateur de topologies ne crée pas de cette instance pour vous.
  

