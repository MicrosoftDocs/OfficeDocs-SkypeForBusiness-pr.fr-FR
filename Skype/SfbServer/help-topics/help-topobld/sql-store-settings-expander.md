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
# <a name="sql-store-settings-expander"></a><span data-ttu-id="55c0d-105">Développement de paramètres SQL magasin</span><span class="sxs-lookup"><span data-stu-id="55c0d-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="55c0d-106">Pour modifier les propriétés d’une base de données SQL Server, vous devez modifier l’instance de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="55c0d-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="55c0d-107">Vous ne pouvez pas utiliser la boîte de dialogue **Modifier les propriétés** pour effectuer des tâches telles que le déplacement de votre base de données du serveur d’archivage à partir d’un ordinateur à un autre.</span><span class="sxs-lookup"><span data-stu-id="55c0d-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="55c0d-108">En outre, vous ne pouvez pas utiliser la boîte de dialogue **Modifier les propriétés** pour modifier l’instance de SQL Server qui héberge le magasin Central de gestion.</span><span class="sxs-lookup"><span data-stu-id="55c0d-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="55c0d-109">Modification des propriétés d’une base de données de SQL Server</span><span class="sxs-lookup"><span data-stu-id="55c0d-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="55c0d-110">Pour modifier l’instance de SQL Server qui est utilisé par une base de données autre que le magasin Central de gestion, procédez comme suit dans le Générateur de topologie :</span><span class="sxs-lookup"><span data-stu-id="55c0d-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="55c0d-111">Pour modifier une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="55c0d-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="55c0d-112">Sélectionnez la base de données appropriée, sous le nœud **stocke de SQL** , puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="55c0d-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="55c0d-113">Dans la boîte de dialogue **Modifier les propriétés** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="55c0d-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
  - <span data-ttu-id="55c0d-114">Pour utiliser l’instance de SQL Server par défaut, sélectionnez **l’Instance par défaut** et puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="55c0d-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
  - <span data-ttu-id="55c0d-115">Pour utiliser une instance nommée de la base de données, sélectionnez **Instance nommée**, entrez le nom de l’instance dans la zone de texte, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="55c0d-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="55c0d-116">Vous devez entrer uniquement le nom de l’instance (par exemple, ArchivingInstance) et pas le chemin entier de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="55c0d-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="55c0d-117">Lorsque vous travaillez dans la boîte de dialogue **Modifier les propriétés** , le Générateur de topologies ne vérifiera pas que l’instance de base de données que vous avez entré est une instance valide.</span><span class="sxs-lookup"><span data-stu-id="55c0d-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="55c0d-118">Par exemple, si vous par inadvertance typeArchivingInstanec comme nom d’instance et puis cliquez sur **OK**, le Générateur de topologies acceptera cette instance non valide.</span><span class="sxs-lookup"><span data-stu-id="55c0d-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="55c0d-119">Avant de pouvoir publier cette topologie, vous devez corriger cette erreur : si une instance de SQL Server ne peut pas être trouvée, le Générateur de topologies ne crée pas de cette instance pour vous.</span><span class="sxs-lookup"><span data-stu-id="55c0d-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

