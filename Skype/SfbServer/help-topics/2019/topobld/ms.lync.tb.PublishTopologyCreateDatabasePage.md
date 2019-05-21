---
title: Créer des bases de données
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: Le générateur de topologie fournit un moyen d’installer des bases de données sur un magasin SQL Server. Lorsque vous installez des bases de données à l’aide du générateur de topologie, l’application lit les informations de la topologie, puis installe les bases de données requises sur l’ordinateur SQL Server spécifié ou le cluster SQL Server. C’est le seul type d’installation de base de données disponible par le biais du générateur de topologie. Si vous avez besoin d’installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données colocalisée, vous devez utiliser l’interface de ligne de commande Windows PowerShell et l’applet de commande Install-CsDatabase.
ms.openlocfilehash: 5736e399771eef30808e62c8a11876d1b6f3d8ed
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302143"
---
# <a name="create-database"></a><span data-ttu-id="3d82b-106">Créer des bases de données</span><span class="sxs-lookup"><span data-stu-id="3d82b-106">Create Database</span></span>
 
<span data-ttu-id="3d82b-107">Le générateur de topologie fournit un moyen d’installer des bases de données sur un magasin SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3d82b-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="3d82b-108">Lorsque vous installez des bases de données à l’aide du générateur de topologie, l’application lit les informations de la topologie, puis installe les bases de données requises sur l’ordinateur SQL Server spécifié ou le cluster SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3d82b-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="3d82b-109">C’est le seul type d’installation de base de données disponible par le biais du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="3d82b-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="3d82b-110">Si vous avez besoin d’installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données colocalisée, vous devez utiliser l’interface de ligne de commande Windows PowerShell et l’applet de commande [install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="3d82b-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="3d82b-111">Création d’une base de données</span><span class="sxs-lookup"><span data-stu-id="3d82b-111">Creating a Database</span></span>

1. <span data-ttu-id="3d82b-112">Cliquez sur le nœud Skype entreprise Server, puis cliquez sur **installer la base de données**.</span><span class="sxs-lookup"><span data-stu-id="3d82b-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="3d82b-113">Dans la boîte de dialogue **installer des bases de données** , dans la page créer une **base de données** , sélectionnez le nom de domaine complet (FQDN) du magasin SQL Server dans lequel les nouvelles bases de données doivent être créées.</span><span class="sxs-lookup"><span data-stu-id="3d82b-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="3d82b-p103">Cliquez sur **Avancé**. Dans la boîte de dialogue **Sélectionner un emplacement de fichier de base de données**, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="3d82b-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="3d82b-p104">**Déterminer automatiquement l’emplacement du fichier de base de données** : si vous sélectionnez cette option, le générateur de topologie utilise un algorithme intégré pour sélectionner l’emplacement de stockage des journaux de bases de données et des fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="3d82b-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="3d82b-118">**Utilisez les valeurs par défaut des instances SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3d82b-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="3d82b-119">Si vous sélectionnez cette option, l’algorithme intégré n’est pas utilisé pour choisir les emplacements de stockage pour les journaux de base de données et les fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="3d82b-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="3d82b-120">Au lieu de cela, les fichiers de données et de journalisation sont stockés dans les emplacements spécifiés par le chemin d’accès par défaut de SQL Server (ces chemins doivent être configurés dans avancé par un administrateur SQL Server).</span><span class="sxs-lookup"><span data-stu-id="3d82b-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="3d82b-121">Les fichiers de données seront stockés dans l’emplacement du fichier de données SQL Server par défaut alors que les fichiers journaux seront stockés dans l’emplacement du fichier journal SQL Server par défaut.</span><span class="sxs-lookup"><span data-stu-id="3d82b-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="3d82b-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d82b-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="3d82b-123">Dans la page **Créer des bases de données**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3d82b-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="3d82b-124">Dans la page **Création de bases de données terminée**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="3d82b-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

