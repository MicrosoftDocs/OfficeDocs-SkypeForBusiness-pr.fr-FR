---
title: 'Lync Server 2013 : exécution de la préparation du schéma'
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
ms.openlocfilehash: 202052ce01bca6cdc11e8ed36dfede9afba74b8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511101"
---
# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="75be2-102">Exécution de la préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75be2-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75be2-103">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="75be2-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="75be2-104">Vous pouvez utiliser le programme d’installation ou les applets de commande Lync Server Management Shell pour préparer le schéma Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75be2-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="75be2-105">L’applet de commande qui étend le schéma Active Directory est **Install-CsAdServerSchema**.</span><span class="sxs-lookup"><span data-stu-id="75be2-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75be2-106">La cmdlet de préparation de schéma (<STRONG>install-CsAdServerSchema</STRONG>) doit accéder au contrôleur de schéma, ce qui nécessite que le service Registre distant soit en cours d’exécution et que la clé de Registre distante soit activée.</span><span class="sxs-lookup"><span data-stu-id="75be2-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="75be2-107">Si le service Registre distant ne peut pas être activé sur le contrôleur de schéma, vous pouvez exécuter l’applet de commande localement sur le contrôleur de schéma.</span><span class="sxs-lookup"><span data-stu-id="75be2-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="75be2-108">Pour plus d’informations sur l’accès à distance au registre, consultez l’article 314837 de la base de connaissances Microsoft, « procédure de gestion de l’accès à distance au registre » à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A> .</span><span class="sxs-lookup"><span data-stu-id="75be2-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="75be2-109">Après avoir préparé le schéma, vérifiez manuellement que la partition du schéma a été répliquée avant de procéder à la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="75be2-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="75be2-110">Pour plus d’informations, consultez [la rubrique vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="75be2-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="75be2-111">Pour utiliser le programme d’installation afin de préparer le schéma de la forêt actuelle</span><span class="sxs-lookup"><span data-stu-id="75be2-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="75be2-112">Ouvrez une session sur un serveur de la forêt en tant que membre du groupe Administrateurs du schéma et avec les droits d’administrateur sur le maître de schémas.</span><span class="sxs-lookup"><span data-stu-id="75be2-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="75be2-113">À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup.exe pour démarrer l’Assistant déploiement.</span><span class="sxs-lookup"><span data-stu-id="75be2-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="75be2-114">Si le système vous invite à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="75be2-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="75be2-115">La boîte de dialogue Configuration de Lync Server 2013 vous invite à indiquer un emplacement d’installation des fichiers Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75be2-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="75be2-116">Choisissez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder à un emplacement de votre choix, puis cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="75be2-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="75be2-117">Dans la page Contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="75be2-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="75be2-118">Le programme d’installation installe les composants principaux de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75be2-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="75be2-119">Lorsque l’Assistant Déploiement est prêt, cliquez sur **Préparer Active Directory** et attendre le résultat quant à l’état du déploiement.</span><span class="sxs-lookup"><span data-stu-id="75be2-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="75be2-120">À l’**Étape 1 : Préparer un schéma**, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="75be2-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="75be2-121">Dans la page **Préparer un schéma**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="75be2-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="75be2-122">Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="75be2-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="75be2-123">Sous la colonne **action** , développez **préparation du schéma**, recherchez le résultat de l' **\<Success\>** exécution à la fin de chaque tâche pour vérifier que la préparation du schéma s’est correctement déroulée, fermez le journal, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="75be2-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="75be2-124">Attendez la fin de la réplication d’Active Directory ou forcez-la.</span><span class="sxs-lookup"><span data-stu-id="75be2-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="75be2-125">Vérifiez manuellement que les modifications de schéma ont été répliquées sur tous les autres contrôleurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="75be2-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="75be2-126">Pour plus d’informations, consultez [la rubrique vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="75be2-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="75be2-127">Pour utiliser des applets de commande afin de préparer le schéma de la forêt actuelle</span><span class="sxs-lookup"><span data-stu-id="75be2-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="75be2-128">Ouvrez une session sur un ordinateur de la forêt en tant que membre du groupe Administrateurs du schéma et avec les droits d’administration sur le contrôleur de schéma.</span><span class="sxs-lookup"><span data-stu-id="75be2-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="75be2-129">Installez les composants principaux de Lync Server comme suit :</span><span class="sxs-lookup"><span data-stu-id="75be2-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="75be2-130">À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup.exe pour démarrer l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75be2-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="75be2-131">Si le système vous invite à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="75be2-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="75be2-132">La boîte de dialogue Configuration de Lync Server 2013 vous invite à indiquer un emplacement d’installation des fichiers Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75be2-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="75be2-133">Choisissez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder à un emplacement de votre choix, puis cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="75be2-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="75be2-134">Dans la page Contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="75be2-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="75be2-135">Le programme d’installation installe les composants principaux de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75be2-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="75be2-136">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="75be2-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="75be2-137">Générer</span><span class="sxs-lookup"><span data-stu-id="75be2-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="75be2-138">Si vous ne spécifiez pas le paramètre LDF, la valeur par défaut est le chemin d’installation de Lync Server 2013 qui est lu à partir du Registre.</span><span class="sxs-lookup"><span data-stu-id="75be2-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="75be2-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="75be2-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="75be2-140">Utilisez l’applet de commande suivante pour vérifier si la préparation de schéma a été exécutée avec succès.</span><span class="sxs-lookup"><span data-stu-id="75be2-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="75be2-141">Cette applet de commande renvoie une valeur de l' \*\* \_ \_ état \_ actuel\*\* de la version du schéma si la préparation du schéma a réussi.</span><span class="sxs-lookup"><span data-stu-id="75be2-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="75be2-142">Attendez la fin de la réplication d’Active Directory ou forcez-la.</span><span class="sxs-lookup"><span data-stu-id="75be2-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="75be2-143">Vérifiez manuellement que les modifications de schéma ont été répliquées sur tous les autres contrôleurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="75be2-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="75be2-144">Pour plus d’informations, consultez [la rubrique vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="75be2-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="75be2-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75be2-145">See Also</span></span>


[<span data-ttu-id="75be2-146">Vérification de la réplication de schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75be2-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="75be2-147">Préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75be2-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

