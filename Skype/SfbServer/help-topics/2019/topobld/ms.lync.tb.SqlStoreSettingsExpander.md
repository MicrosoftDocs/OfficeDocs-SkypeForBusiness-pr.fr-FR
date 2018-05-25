---
title: Expanseur des paramètres du magasin SQL
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
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="075d3-105">Expanseur des paramètres du magasin SQL</span><span class="sxs-lookup"><span data-stu-id="075d3-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="075d3-106">Pour modifier les propriétés d’une base de données SQL Server, vous devez modifier l’instance de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="075d3-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="075d3-107">Vous ne pouvez pas utiliser la boîte de dialogue **Modifier les propriétés** pour effectuer des tâches telles que le déplacement de votre base de données du serveur d’archivage à partir d’un ordinateur à un autre.</span><span class="sxs-lookup"><span data-stu-id="075d3-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="075d3-108">En outre, vous ne pouvez pas utiliser la boîte de dialogue **Modifier les propriétés** pour modifier l’instance de SQL Server qui héberge le magasin Central de gestion.</span><span class="sxs-lookup"><span data-stu-id="075d3-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="075d3-109">Modification des propriétés d’une base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="075d3-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="075d3-110">Pour changer l’instance de SQL Server qui est utilisée par toute base de données autre que le magasin Central de gestion, effectuez la procédure suivante dans le Générateur de topologie :</span><span class="sxs-lookup"><span data-stu-id="075d3-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="075d3-111">Pour modifier une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="075d3-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="075d3-112">Sélectionnez la base de données appropriée sous le nœud **stocke SQL** , puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="075d3-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="075d3-113">Dans la boîte de dialogue **Modifier les propriétés** , effectuez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="075d3-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
  - <span data-ttu-id="075d3-114">Pour utiliser l’instance de SQL Server par défaut, sélectionnez **Instance par défaut** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="075d3-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
  - <span data-ttu-id="075d3-115">Pour utiliser une instance nommée de la base de données, sélectionnez **Instance nommée**, entrez le nom de l’instance dans la zone de texte, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="075d3-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="075d3-116">Vous devez entrer uniquement le nom d’instance (par exemple, ArchivingInstance) et pas le chemin entier de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="075d3-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="075d3-117">Lorsque vous travaillez dans la boîte de dialogue **Modifier les propriétés** , le Générateur de topologie pas vérifie que l’instance de base de données que vous avez entré est une instance valide.</span><span class="sxs-lookup"><span data-stu-id="075d3-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="075d3-118">Par exemple, si vous par inadvertance typeArchivingInstanec comme nom d’instance et puis cliquez sur **OK**, le Générateur de topologie acceptera cette instance non valide.</span><span class="sxs-lookup"><span data-stu-id="075d3-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="075d3-119">Avant de pouvoir publier cette topologie, vous devez corriger cette erreur : si une instance SQL Server est introuvable, le Générateur de topologie ne crée pas de cette instance pour vous.</span><span class="sxs-lookup"><span data-stu-id="075d3-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

