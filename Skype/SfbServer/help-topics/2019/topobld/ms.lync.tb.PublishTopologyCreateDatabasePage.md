---
title: Créer des bases de données
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: Générateur de topologies permet d’installer les bases de données sur un magasin SQL Server. Lorsque vous installez les bases de données à l’aide du Générateur de topologie, l’application lit les informations de la topologie de, puis installe les bases de données requises sur l’ordinateur SQL Server spécifié ou d’un cluster SQL Server. C’est le seul type d’installation de base de données disponible par le biais du générateur de topologie. Si vous avez besoin installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données colocalisée, vous devez utiliser à la place interface de ligne de commande Windows PowerShell et l’applet de commande Install-CsDatabase.
ms.openlocfilehash: db163598ff5116e1f42dbb4a52d1d4fcbda18081
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919737"
---
# <a name="create-database"></a><span data-ttu-id="f4901-106">Créer des bases de données</span><span class="sxs-lookup"><span data-stu-id="f4901-106">Create Database</span></span>
 
<span data-ttu-id="f4901-107">Générateur de topologies permet d’installer les bases de données sur un magasin SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4901-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="f4901-108">Lorsque vous installez les bases de données à l’aide du Générateur de topologie, l’application lit les informations de la topologie de, puis installe les bases de données requises sur l’ordinateur SQL Server spécifié ou d’un cluster SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4901-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="f4901-109">C’est le seul type d’installation de base de données disponible par le biais du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="f4901-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="f4901-110">Si vous avez besoin installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données colocalisée, vous devez utiliser à la place interface de ligne de commande Windows PowerShell et l’applet de commande [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f4901-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="f4901-111">Création d’une base de données</span><span class="sxs-lookup"><span data-stu-id="f4901-111">Creating a Database</span></span>

1. <span data-ttu-id="f4901-112">Cliquez sur le Skype pour le nœud du serveur d’entreprise, puis cliquez sur **Installer une base de données**.</span><span class="sxs-lookup"><span data-stu-id="f4901-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="f4901-113">Dans la boîte de dialogue **Installer les bases de données** , dans la page **Créer une base de données** , sélectionnez le nom de domaine complet (FQDN) du magasin SQL Server où les nouvelles bases de données sont créées.</span><span class="sxs-lookup"><span data-stu-id="f4901-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="f4901-p103">Cliquez sur **Avancé**. Dans la boîte de dialogue **Sélectionner un emplacement de fichier de base de données**, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f4901-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="f4901-p104">**Déterminer automatiquement l’emplacement du fichier de base de données** : si vous sélectionnez cette option, le générateur de topologie utilise un algorithme intégré pour sélectionner l’emplacement de stockage des journaux de bases de données et des fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="f4901-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="f4901-118">**Utiliser SQL Server instance par défaut**.</span><span class="sxs-lookup"><span data-stu-id="f4901-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="f4901-119">Si vous sélectionnez cette option, l’algorithme intégré n’est pas utilisé pour choisir les emplacements de stockage pour les journaux de base de données et les fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="f4901-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="f4901-120">Au lieu de cela, les fichiers journaux et de données sont stockés dans les emplacements spécifiés par le chemin d’accès par défaut de SQL Server (les chemins d’accès doivent être configurés dans avancée par un administrateur de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="f4901-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="f4901-121">Fichiers de données seront stockés dans l’emplacement de fichier de données SQL Server par défaut pendant que les fichiers journaux seront stockés dans l’emplacement du fichier journal SQL Server par défaut.</span><span class="sxs-lookup"><span data-stu-id="f4901-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="f4901-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4901-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="f4901-123">Dans la page **Créer des bases de données**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f4901-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="f4901-124">Dans la page **Création de bases de données terminée**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f4901-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

