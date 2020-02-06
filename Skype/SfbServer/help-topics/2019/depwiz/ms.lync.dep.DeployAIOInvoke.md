---
title: Préparer le serveur Standard Edition (appel)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: Sur la page exécution des commandes, les tâches d’installation de SQL Server Express et de configuration pour fonctionner en tant que magasin de gestion centrale peuvent être affichées dans le volet Office. Par défaut, une instance de base de données SQL Server nommée RTC est créée. Des règles de pare-feu sont également créées pour autoriser l’accès entrant et sortant aux serveurs et clients pour communiquer avec la base de données et l’instance. Une fois la tâche effectuée, vous pouvez sélectionner le fichier journal dans la liste déroulante. Le fichier journal porte le nom de l’ordinateur local bootstrap. Après avoir sélectionné le fichier journal, cliquez sur Afficher le journal. Examinez le fichier journal pour afficher les erreurs et les avertissements. Lorsque vous êtes prêt à poursuivre, cliquez sur Terminer. Si ce n’est déjà fait, vous devez maintenant définir votre topologie avec le générateur de topologie.
ms.openlocfilehash: 0a1b8245df8e50ba4da73c98e9dcb865446a0ecc
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796965"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="96371-111">Préparer le serveur Standard Edition (appel)</span><span class="sxs-lookup"><span data-stu-id="96371-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="96371-112">Sur la page **exécution des commandes** , les tâches d’installation de SQL Server Express et de configuration pour fonctionner en tant que magasin de gestion centrale peuvent être affichées dans le volet Office.</span><span class="sxs-lookup"><span data-stu-id="96371-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="96371-113">Par défaut, une instance de base de données SQL Server nommée RTC est créée.</span><span class="sxs-lookup"><span data-stu-id="96371-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="96371-114">Des règles de pare-feu sont également créées pour autoriser l’accès entrant et sortant aux serveurs et clients pour communiquer avec la base de données et l’instance.</span><span class="sxs-lookup"><span data-stu-id="96371-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="96371-115">Une fois la tâche effectuée, vous pouvez sélectionner le fichier journal dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="96371-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="96371-116">Le fichier journal porte le nom de l' **ordinateur local bootstrap**.</span><span class="sxs-lookup"><span data-stu-id="96371-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="96371-117">Après avoir sélectionné le fichier journal, cliquez sur **afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="96371-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="96371-118">Examinez le fichier journal pour afficher les erreurs et les avertissements.</span><span class="sxs-lookup"><span data-stu-id="96371-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="96371-119">Lorsque vous êtes prêt à poursuivre, cliquez sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="96371-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="96371-120">Si ce n’est déjà fait, vous devez maintenant définir votre topologie avec le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="96371-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="96371-121">L’installation de SQL Server Express peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="96371-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="96371-122">Lors de l’installation, aucune progression n’est visible à l’écran ou par le volet Office.</span><span class="sxs-lookup"><span data-stu-id="96371-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="96371-123">Pour surveiller l’installation, utilisez le gestionnaire des tâches Windows et recherchez les processus MSIExec et les fichiers d’installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="96371-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="96371-124">De cette façon, vous pouvez afficher l’état de l’installation et vérifier qu’elle est en cours d’installation.</span><span class="sxs-lookup"><span data-stu-id="96371-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="96371-125">Selon les facteurs au-delà de la portée de cette rubrique d’aide, l’installation de l’instance SQL Server peut prendre jusqu’à 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="96371-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

