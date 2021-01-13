---
title: Créer des bases de données
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: Le Générateur de topologie permet d’installer des bases de données sur SQL Server magasin. Lorsque vous installez des bases de données à l’aide du Générateur de topologie, l’application lit les informations de la topologie, puis installe les bases de données requises sur l’ordinateur SQL Server ou le cluster SQL Server spécifié. C’est le seul type d’installation de base de données disponible par le biais du Générateur de topologie. Si vous devez installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données c collocée, vous devez utiliser l’interface de ligne de commande Windows PowerShell et l’cmdlet Install-CsDatabase à la place.
ms.openlocfilehash: 1092840305d1a455aa094776ae757cf074f7e89a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822284"
---
# <a name="create-database"></a><span data-ttu-id="ebfa5-106">Création de base de données</span><span class="sxs-lookup"><span data-stu-id="ebfa5-106">Create Database</span></span>
 
<span data-ttu-id="ebfa5-107">Le Générateur de topologie permet d’installer des bases de données sur SQL Server magasin.</span><span class="sxs-lookup"><span data-stu-id="ebfa5-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="ebfa5-108">Lorsque vous installez des bases de données à l’aide du Générateur de topologie, l’application lit les informations de la topologie, puis installe les bases de données requises sur l’ordinateur SQL Server ou le cluster SQL Server spécifié.</span><span class="sxs-lookup"><span data-stu-id="ebfa5-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="ebfa5-109">C’est le seul type d’installation de base de données disponible par le biais du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="ebfa5-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="ebfa5-110">Si vous avez besoin d’installer une base de données spécifique sur un ordinateur spécifique, ou si vous devez installer une base de données CsDatabase, vous devez utiliser l’interface de ligne de commande Windows PowerShell et l’cmdlet [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) à la place.</span><span class="sxs-lookup"><span data-stu-id="ebfa5-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="ebfa5-111">Création d’une base de données</span><span class="sxs-lookup"><span data-stu-id="ebfa5-111">Creating a Database</span></span>

1. <span data-ttu-id="ebfa5-112">Cliquez sur le nœud Skype Entreprise Server, puis sur Installer la base **de données.**</span><span class="sxs-lookup"><span data-stu-id="ebfa5-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="ebfa5-113">Dans  la boîte de dialogue Installer des bases de données, dans la **page** Créer une base de données, sélectionnez le nom de domaine complet (FQDN) du magasin SQL Server où les nouvelles bases de données doivent être créées.</span><span class="sxs-lookup"><span data-stu-id="ebfa5-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="ebfa5-p103">Cliquez sur **Avancé**. Dans la boîte de dialogue **Sélectionner un emplacement de fichier de base de données**, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="ebfa5-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="ebfa5-p104">**Déterminer automatiquement l’emplacement du fichier de base de données**. Si vous sélectionnez cette option, le Générateur de topologie utilise un algorithme intégré pour choisir l’emplacement de stockage pour les journaux de bases de données et les fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="ebfa5-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="ebfa5-118">**Utiliser les valeurs par défaut de l’instance SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ebfa5-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="ebfa5-119">Si vous sélectionnez cette option, l’algorithme intégré n’est pas utilisé pour choisir les emplacements de stockage pour les journaux de bases de données et les fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="ebfa5-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="ebfa5-120">À la place, les fichiers journaux et les fichiers de données sont stockés aux emplacements spécifiés dans les chemins d’accès SQL Server par défaut (ces chemins doivent être configurés à l’avance par un administrateur SQL).</span><span class="sxs-lookup"><span data-stu-id="ebfa5-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="ebfa5-121">Les fichiers de données seront stockés à l’emplacement attribué par défaut pour les fichiers de données SQL Server et les fichiers journaux SQL Server à leur emplacement défini par défaut.</span><span class="sxs-lookup"><span data-stu-id="ebfa5-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="ebfa5-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ebfa5-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="ebfa5-123">Dans la page **Créer des bases de données**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ebfa5-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="ebfa5-124">Dans la page **Création de bases de données terminée**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="ebfa5-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

