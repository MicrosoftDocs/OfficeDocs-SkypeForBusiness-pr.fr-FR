---
title: Expanseur des paramètres du magasin SQL
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Pour modifier les propriétés d’une base SQL Server de données, vous devez modifier l’instance SQL Server base de données. Vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour effectuer des tâches comme le déplacement de votre base de données de serveur d’archivage d’un ordinateur sur un autre. En outre, vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour modifier l’instance de SQL Server qui héberge le magasin central de gestion.
ms.openlocfilehash: b57d4e1bae0b3ea03470ffa8284f26260ff21381
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410037"
---
# <a name="sql-store-settings-expander"></a>Expandeur des paramètres du magasin SQL
 
Pour modifier les propriétés d’une base SQL Server de données, vous devez modifier l’instance SQL Server base de données. Vous ne pouvez pas utiliser la boîte de dialogue **Modifier les propriétés** pour effectuer des tâches comme le déplacement de votre base de données de serveur d’archivage d’un ordinateur sur un autre. En outre, vous ne pouvez pas  utiliser la boîte de dialogue Modifier les propriétés pour modifier l’instance de SQL Server qui héberge le magasin central de gestion.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Modification des propriétés d’une base de données SQL Server données

Pour modifier l’instance de SQL Server utilisée par une base de données autre que le magasin central de gestion, complétez la procédure suivante dans le Générateur de topologie :
  
### <a name="to-modify-an-instance-of-sql-server"></a>Pour modifier une instance de SQL Server

1. Sélectionnez la base de données qui convient sous le nœud **Magasins SQL**, puis cliquez sur **Modifier les propriétés**.
    
2. Dans la boîte de dialogue **Modifier les propriétés**, effectuez l’une des opérations suivantes :
    
   - Pour utiliser l’instance SQL Server par défaut, sélectionnez **Instance** par défaut, puis cliquez sur **OK**.
    
   - Pour utiliser une instance de base de données nommée, sélectionnez **Instance nommée**, entrez le nom de l’instance dans la zone de texte, puis cliquez sur **OK**. Vous devez entrer uniquement le nom de l’instance (par exemple, ArchivingInstance), et non l’intégralité SQL Server chemin d’accès.
    
Lorsque vous travaillez dans la boîte  de dialogue Modifier les propriétés, le Générateur de topologie ne vérifie pas que l’instance de base de données que vous avez entrée est une instance valide. Par exemple, si vous tapez par inadvertanceArchivingInstanec comme nom d’instance, puis cliquez sur **OK**, le Générateur de topologie acceptera cette instance non valide. Avant de publier cette topologie, vous devez corriger cette erreur : si une instance SQL Server est in trouvée, le Générateur de topologie ne créera pas cette instance pour vous.
  

