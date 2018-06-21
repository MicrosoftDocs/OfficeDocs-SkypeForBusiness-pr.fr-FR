---
title: Expanseur des paramètres du magasin SQL
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Pour modifier les propriétés d’une base de données SQL Server, vous devez modifier l’instance de base de données SQL Server. Vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour effectuer des tâches telles que le déplacement de votre base de données du serveur d’archivage à partir d’un ordinateur à un autre. En outre, vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour modifier l’instance de SQL Server qui héberge le magasin Central de gestion.
ms.openlocfilehash: d9ba91dca9cb6e0e779f154925a4d00065458866
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19972230"
---
# <a name="sql-store-settings-expander"></a>Expanseur des paramètres du magasin SQL
 
Pour modifier les propriétés d’une base de données SQL Server, vous devez modifier l’instance de base de données SQL Server. Vous ne pouvez pas utiliser la boîte de dialogue **Modifier les propriétés** pour effectuer des tâches telles que le déplacement de votre base de données du serveur d’archivage à partir d’un ordinateur à un autre. En outre, vous ne pouvez pas utiliser la boîte de dialogue **Modifier les propriétés** pour modifier l’instance de SQL Server qui héberge le magasin Central de gestion.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Modification des propriétés d’une base de données SQL Server

Pour changer l’instance de SQL Server qui est utilisée par toute base de données autre que le magasin Central de gestion, effectuez la procédure suivante dans le Générateur de topologie :
  
### <a name="to-modify-an-instance-of-sql-server"></a>Pour modifier une instance de SQL Server

1. Sélectionnez la base de données appropriée sous le nœud **stocke SQL** , puis cliquez sur **Modifier les propriétés**.
    
2. Dans la boîte de dialogue **Modifier les propriétés** , effectuez l’une des options suivantes :
    
  - Pour utiliser l’instance de SQL Server par défaut, sélectionnez **Instance par défaut** , puis cliquez sur **OK**.
    
  - Pour utiliser une instance nommée de la base de données, sélectionnez **Instance nommée**, entrez le nom de l’instance dans la zone de texte, puis cliquez sur **OK**. Vous devez entrer uniquement le nom d’instance (par exemple, ArchivingInstance) et pas le chemin entier de SQL Server.
    
Lorsque vous travaillez dans la boîte de dialogue **Modifier les propriétés** , le Générateur de topologie pas vérifie que l’instance de base de données que vous avez entré est une instance valide. Par exemple, si vous par inadvertance typeArchivingInstanec comme nom d’instance et puis cliquez sur **OK**, le Générateur de topologie acceptera cette instance non valide. Avant de pouvoir publier cette topologie, vous devez corriger cette erreur : si une instance SQL Server est introuvable, le Générateur de topologie ne crée pas de cette instance pour vous.
  

