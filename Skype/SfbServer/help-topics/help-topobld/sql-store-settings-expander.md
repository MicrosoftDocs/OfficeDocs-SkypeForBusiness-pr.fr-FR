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
# <a name="sql-store-settings-expander"></a><span data-ttu-id="4232e-105">Expanseur des paramètres du magasin SQL</span><span class="sxs-lookup"><span data-stu-id="4232e-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="4232e-106">Pour modifier les propriétés d’une base de données SQL Server, vous devez modifier l’instance de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4232e-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="4232e-107">Vous ne pouvez pas utiliser la boîte de dialogue **Modifier les propriétés** pour effectuer des tâches comme le déplacement de votre base de données de serveur d’archivage d’un ordinateur sur un autre.</span><span class="sxs-lookup"><span data-stu-id="4232e-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="4232e-108">De plus, vous ne pouvez pas utiliser la boîte de dialogue **modifier les propriétés** pour modifier l’instance de SQL Server qui héberge le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="4232e-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="4232e-109">Modification des propriétés d’une base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="4232e-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="4232e-110">Pour modifier l’instance de SQL Server utilisée par une autre base de données que le magasin central de gestion, effectuez la procédure suivante dans le générateur de topologie :</span><span class="sxs-lookup"><span data-stu-id="4232e-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="4232e-111">Pour modifier une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4232e-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="4232e-112">Sélectionnez la base de données qui convient sous le nœud **Magasins SQL**, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4232e-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="4232e-113">Dans la boîte de dialogue **Modifier les propriétés**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4232e-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="4232e-114">Pour utiliser l’instance par défaut de SQL Server, sélectionnez **instance par défaut** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4232e-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="4232e-115">Pour utiliser une instance de base de données nommée, sélectionnez **Instance nommée**, entrez le nom de l’instance dans la zone de texte, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4232e-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="4232e-116">Vous devez entrer uniquement le nom de l’instance (par exemple, ArchivingInstance), et non l’intégralité du chemin SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4232e-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="4232e-117">Lorsque vous utilisez la boîte de dialogue **modifier les propriétés** , le générateur de topologie ne vérifie pas que l’instance de base de données que vous avez entrée est une instance valide.</span><span class="sxs-lookup"><span data-stu-id="4232e-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="4232e-118">Par exemple, si vous typeArchivingInstanec par inadvertance comme nom d’instance, puis que vous cliquez sur **OK**, le générateur de topologies acceptera cette instance incorrecte.</span><span class="sxs-lookup"><span data-stu-id="4232e-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="4232e-119">Avant de pouvoir publier cette topologie, vous devez corriger cette erreur : si une instance de SQL Server est introuvable, le générateur de topologie ne créera pas cette instance pour vous.</span><span class="sxs-lookup"><span data-stu-id="4232e-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

