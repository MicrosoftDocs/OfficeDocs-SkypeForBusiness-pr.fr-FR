---
title: Expanseur des paramètres du magasin SQL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Pour modifier les propriétés d’une base de données SQL Server, vous devez modifier l’instance de base de données SQL Server. Vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour effectuer des tâches comme le déplacement de votre base de données de serveur d’archivage d’un ordinateur sur un autre. De plus, vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour modifier l’instance de SQL Server qui héberge le magasin central de gestion.
ms.openlocfilehash: e3b16d8c6eab4f4918ef39b3c4f1ab4d0c6fc057
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219609"
---
# <a name="sql-store-settings-expander"></a>Expanseur des paramètres du magasin SQL
 
Pour modifier les propriétés d’une base de données SQL Server, vous devez modifier l’instance de base de données SQL Server. Vous ne pouvez pas utiliser la boîte de dialogue **Modifier les propriétés** pour effectuer des tâches comme le déplacement de votre base de données de serveur d’archivage d’un ordinateur sur un autre. De plus, vous ne pouvez pas utiliser la boîte de dialogue **modifier les propriétés** pour modifier l’instance de SQL Server qui héberge le magasin central de gestion.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Modification des propriétés d’une base de données SQL Server

Pour modifier l’instance de SQL Server utilisée par une autre base de données que le magasin central de gestion, effectuez la procédure suivante dans le générateur de topologie :
  
### <a name="to-modify-an-instance-of-sql-server"></a>Pour modifier une instance de SQL Server

1. Sélectionnez la base de données qui convient sous le nœud **Magasins SQL**, puis cliquez sur **Modifier les propriétés**.
    
2. Dans la boîte de dialogue **Modifier les propriétés**, effectuez l’une des opérations suivantes :
    
   - Pour utiliser l’instance par défaut de SQL Server, sélectionnez **instance par défaut** , puis cliquez sur **OK**.
    
   - Pour utiliser une instance de base de données nommée, sélectionnez **Instance nommée**, entrez le nom de l’instance dans la zone de texte, puis cliquez sur **OK**. Vous devez entrer uniquement le nom de l’instance (par exemple, ArchivingInstance), et non l’intégralité du chemin SQL Server.
    
Lorsque vous utilisez la boîte de dialogue **modifier les propriétés** , le générateur de topologie ne vérifie pas que l’instance de base de données que vous avez entrée est une instance valide. Par exemple, si vous typeArchivingInstanec par inadvertance comme nom d’instance, puis que vous cliquez sur **OK**, le générateur de topologies acceptera cette instance incorrecte. Avant de pouvoir publier cette topologie, vous devez corriger cette erreur : si une instance de SQL Server est introuvable, le générateur de topologie ne créera pas cette instance pour vous.
  

