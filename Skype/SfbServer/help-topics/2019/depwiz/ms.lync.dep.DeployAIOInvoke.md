---
title: Préparer le serveur Standard Edition (appeler)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Dans la page Exécution de commandes, les tâches d’installation de SQL Server Express et de configuration pour agir en tant que magasin central de gestion peuvent être vues dans le volet Des tâches. Par défaut, une instance d’une base SQL Server basée sur SQL Server appelée RTC est créée. Des règles de pare-feu sont également créées pour autoriser l’accès entrant et sortant des clients et des serveurs en vue de communiquer avec la base de données et l’instance. Une fois la tâche achevée, vous pouvez sélectionner le fichier journal dans la liste déroulante. Le fichier journal s’appelle Démarrage de la machine locale. Une fois le fichier journal sélectionné, cliquez sur Afficher le journal. Recherchez de possibles erreurs et avertissements dans le fichier journal. Lorsque vous êtes prêt à continuer, cliquez sur Terminer. Vous devez maintenant définir votre topologie avec le Générateur de topologie si vous ne l’avez pas déjà fait.
ms.openlocfilehash: c3e6e01f7aed0471d8f1eed0ad79f8ef6320f86a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820614"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="1f8d8-111">Préparer le serveur Standard Edition (appeler)</span><span class="sxs-lookup"><span data-stu-id="1f8d8-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="1f8d8-112">Dans **la** page Exécution de commandes, les tâches d’installation de SQL Server Express et de configuration pour agir en tant que magasin central de gestion peuvent être vues dans le volet Des tâches.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="1f8d8-113">Par défaut, une instance d’une base SQL Server basée sur SQL Server appelée RTC est créée.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="1f8d8-114">Des règles de pare-feu sont également créées pour autoriser l’accès entrant et sortant des clients et des serveurs en vue de communiquer avec la base de données et l’instance.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="1f8d8-115">Une fois la tâche achevée, vous pouvez sélectionner le fichier journal dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="1f8d8-116">Le fichier journal s’appelle **Démarrage de la machine locale**.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="1f8d8-117">Une fois le fichier journal sélectionné, cliquez sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="1f8d8-118">Recherchez de possibles erreurs et avertissements dans le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="1f8d8-119">Lorsque vous êtes prêt à continuer, cliquez sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="1f8d8-120">Vous devez maintenant définir votre topologie avec le Générateur de topologie si vous ne l’avez pas déjà fait.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1f8d8-121">L’installation de SQL Server Express peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="1f8d8-122">Aucune barre de progression n’est visible à l’écran ou dans le volet des tâches pendant l’installation.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="1f8d8-123">Pour surveiller l’installation, vous devez utiliser le Gestionnaire des tâches Windows et rechercher les processus MSIExec et les fichiers d’installation pour SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="1f8d8-124">Ainsi, vous pouvez voir le statut de l’installation et vous assurer de sa progression.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="1f8d8-125">Selon des facteurs au-delà de la portée de cette rubrique d’aide, l’installation de l’instance de SQL Server peut prendre jusqu’à 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

