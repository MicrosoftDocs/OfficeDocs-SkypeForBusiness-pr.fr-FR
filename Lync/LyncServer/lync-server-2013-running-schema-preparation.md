---
title: 'Lync Server 2013 : Exécution de la préparation du schéma'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06b02981e9baa589801839c8fd8c871ae35b0dde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="ae4e9-102">Exécution de la préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae4e9-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae4e9-103">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ae4e9-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="ae4e9-104">Vous pouvez utiliser le programme d’installation ou les applets de contrôle Lync Server Management Shell pour préparer le schéma Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="ae4e9-105">L’applet de contrôle qui étend le schéma Active Directory est **install-CsAdServerSchema**.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae4e9-106">L’applet de commande de préparation du schéma (<STRONG>install-CsAdServerSchema</STRONG>) doit accéder au maître de schéma, qui nécessite que le service Registre distant soit en cours d’exécution et que la clé de Registre à distance soit activée.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="ae4e9-107">Si le service Registre distant ne peut pas être activé sur le maître de schéma, vous pouvez exécuter l’applet de commande localement sur le maître de schéma.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="ae4e9-108">Pour plus d’informations sur l’accès à distance du Registre, voir l’article de la base de connaissances Microsoft 314837, « comment gérer <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>l’accès distant au registre ».</span><span class="sxs-lookup"><span data-stu-id="ae4e9-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="ae4e9-109">Après avoir terminé la préparation du schéma, vérifiez manuellement que la partition de schéma a été répliquée avant de procéder à la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="ae4e9-110">Pour plus d’informations, consultez [vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ae4e9-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="ae4e9-111">Pour utiliser le programme d’installation pour préparer le schéma de la forêt actuelle</span><span class="sxs-lookup"><span data-stu-id="ae4e9-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="ae4e9-112">Ouvrez une session sur un serveur de votre forêt en tant que membre du groupe administrateurs de schéma et avec des droits d’administrateur sur le maître de schéma.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="ae4e9-113">À partir du dossier d’installation ou du média de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant déploiement.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="ae4e9-114">Si vous êtes invité à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="ae4e9-115">La boîte de dialogue de configuration de Lync Server 2013 vous invite à entrer un emplacement d’installation des fichiers du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="ae4e9-116">Choisissez l’emplacement par défaut ou **Naviguez** jusqu’à l’emplacement de votre choix, puis cliquez sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="ae4e9-117">Sur la page contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="ae4e9-118">Le programme d’installation installe les composants principaux de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="ae4e9-119">Lorsque l’Assistant déploiement est prêt, cliquez sur **Préparer Active Directory**et attendez que l’état du déploiement soit déterminé.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="ae4e9-120">À l' **étape 1 : préparer le schéma**, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="ae4e9-121">Sur la page **préparer le schéma** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="ae4e9-122">Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="ae4e9-123">Sous la colonne **action** , développez **préparation du schéma**, recherchez le \*\* \<\> \*\* résultat de réussite d’exécution à la fin de chaque tâche pour vérifier que la préparation du schéma s’est déroulée correctement, fermez le journal, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="ae4e9-124">Attendez la fin de la réplication Active Directory pour qu’elle soit terminée ou forcée.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="ae4e9-125">Assurez-vous manuellement que les modifications du schéma sont répliquées sur tous les autres contrôleurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="ae4e9-126">Pour plus d’informations, consultez [vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ae4e9-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="ae4e9-127">Pour utiliser des applets de cmdlet pour préparer le schéma de la forêt actuelle</span><span class="sxs-lookup"><span data-stu-id="ae4e9-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="ae4e9-128">Ouvrez une session sur un ordinateur de la forêt en tant que membre du groupe administrateurs de schéma et avec des droits d’administrateur sur le maître de schéma.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="ae4e9-129">Installez les composants principaux de Lync Server comme suit :</span><span class="sxs-lookup"><span data-stu-id="ae4e9-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="ae4e9-130">À partir du dossier d’installation ou du média de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="ae4e9-131">Si vous êtes invité à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="ae4e9-132">La boîte de dialogue de configuration de Lync Server 2013 vous invite à entrer un emplacement d’installation des fichiers du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="ae4e9-133">Choisissez l’emplacement par défaut ou **Naviguez** jusqu’à l’emplacement de votre choix, puis cliquez sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="ae4e9-134">Sur la page contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="ae4e9-135">Le programme d’installation installe les composants principaux de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="ae4e9-136">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="ae4e9-137">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="ae4e9-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="ae4e9-138">Si vous ne spécifiez pas le paramètre LDF, la valeur par défaut correspond au chemin d’accès de l’installation de Lync Server 2013 lu à partir du Registre.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="ae4e9-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ae4e9-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="ae4e9-140">Utilisez l’applet de commande suivante pour vérifier que la préparation du schéma s’est terminée.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="ae4e9-141">Cette applet de contrôle renvoie une valeur de l' **état\_\_\_de version du schéma en cours** si la préparation du schéma a réussi.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="ae4e9-142">Attendez la fin de la réplication Active Directory pour qu’elle soit terminée ou forcée.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="ae4e9-143">Assurez-vous manuellement que les modifications du schéma sont répliquées sur tous les autres contrôleurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="ae4e9-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="ae4e9-144">Pour plus d’informations, consultez [vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ae4e9-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ae4e9-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ae4e9-145">See Also</span></span>


[<span data-ttu-id="ae4e9-146">Vérification de la réplication de schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae4e9-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="ae4e9-147">Préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae4e9-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

