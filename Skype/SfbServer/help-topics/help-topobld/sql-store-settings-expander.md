---
title: Expanseur des paramètres du magasin SQL
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Pour modifier les propriétés d’une base SQL Server de données, vous devez modifier l’instance SQL Server base de données. Vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour effectuer des tâches comme le déplacement de votre base de données de serveur d’archivage d’un ordinateur sur un autre. En outre, vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour modifier l’instance de SQL Server qui héberge le magasin central de gestion.
ms.openlocfilehash: d6601349afcc458fc4ba8c3f4feb8810a9c71c42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818094"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="ca675-105">Expandeur des paramètres du magasin SQL</span><span class="sxs-lookup"><span data-stu-id="ca675-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="ca675-106">Pour modifier les propriétés d’une base SQL Server de données, vous devez modifier l’instance SQL Server base de données.</span><span class="sxs-lookup"><span data-stu-id="ca675-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="ca675-107">Vous ne pouvez pas utiliser la boîte de dialogue **Modifier les propriétés** pour effectuer des tâches comme le déplacement de votre base de données de serveur d’archivage d’un ordinateur sur un autre.</span><span class="sxs-lookup"><span data-stu-id="ca675-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="ca675-108">En outre, vous  ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés pour modifier l’instance de SQL Server qui héberge le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="ca675-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="ca675-109">Modification des propriétés d’une base de données SQL Server données</span><span class="sxs-lookup"><span data-stu-id="ca675-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="ca675-110">Pour modifier l’instance de SQL Server utilisée par une base de données autre que le magasin central de gestion, complétez la procédure suivante dans le Générateur de topologie :</span><span class="sxs-lookup"><span data-stu-id="ca675-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="ca675-111">Pour modifier une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca675-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="ca675-112">Sélectionnez la base de données qui convient sous le nœud **Magasins SQL**, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ca675-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="ca675-113">Dans la boîte de dialogue **Modifier les propriétés**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ca675-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="ca675-114">Pour utiliser l’instance SQL Server par défaut, sélectionnez **Instance** par défaut, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="ca675-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="ca675-115">Pour utiliser une instance de base de données nommée, sélectionnez **Instance nommée**, entrez le nom de l’instance dans la zone de texte, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca675-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="ca675-116">Vous devez entrer uniquement le nom de l’instance (par exemple, ArchivingInstance), et non l’intégralité SQL Server chemin d’accès.</span><span class="sxs-lookup"><span data-stu-id="ca675-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="ca675-117">Lorsque vous travaillez  dans la boîte de dialogue Modifier les propriétés, le Générateur de topologie ne vérifie pas que l’instance de base de données que vous avez entrée est une instance valide.</span><span class="sxs-lookup"><span data-stu-id="ca675-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="ca675-118">Par exemple, si vous tapez par inadvertanceArchivingInstanec comme nom d’instance, puis cliquez sur **OK**, le Générateur de topologie acceptera cette instance non valide.</span><span class="sxs-lookup"><span data-stu-id="ca675-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="ca675-119">Avant de publier cette topologie, vous devez corriger cette erreur : si une instance SQL Server est in trouvée, le Générateur de topologie ne créera pas cette instance pour vous.</span><span class="sxs-lookup"><span data-stu-id="ca675-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

