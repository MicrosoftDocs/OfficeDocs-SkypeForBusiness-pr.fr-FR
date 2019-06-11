---
title: 'Lync Server 2013 : Exécution de la préparation de la forêt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b011623b9091c1c707ae77381dacb99ba4642a21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="142ac-102">Exécution de la préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="142ac-102">Running forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="142ac-103">_**Dernière modification de la rubrique:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="142ac-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="142ac-104">Vous pouvez utiliser les applets de applet de configuration ou Lync Server Management Shell pour préparer la forêt.</span><span class="sxs-lookup"><span data-stu-id="142ac-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="142ac-105">L’applet de cmdlet qui prépare la forêt est **Enable-CsAdForest**.</span><span class="sxs-lookup"><span data-stu-id="142ac-105">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="142ac-106">Après avoir préparé la forêt, vous devez vérifier que les paramètres globaux ont été répliqués avant d’exécuter la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="142ac-106">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="142ac-107">Pour préparer la forêt à l’aide du programme d’installation</span><span class="sxs-lookup"><span data-stu-id="142ac-107">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="142ac-108">Ouvrez une session sur un ordinateur qui est joint à un domaine en tant que membre du groupe administrateurs d’entreprise pour le domaine racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="142ac-108">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="142ac-109">À partir du dossier d’installation ou du média de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant déploiement.</span><span class="sxs-lookup"><span data-stu-id="142ac-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="142ac-110">Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.</span><span class="sxs-lookup"><span data-stu-id="142ac-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="142ac-111">À l' **étape 3: préparer la forêt actuelle**, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="142ac-111">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="142ac-112">Sur la page **préparer la forêt** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="142ac-112">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="142ac-113">La préparation de la forêt vous permet de choisir où placer les groupes universels pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="142ac-113">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="142ac-114">Sélectionnez un emplacement conforme aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="142ac-114">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="142ac-115">Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="142ac-115">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="142ac-116">Sous la colonne **action** , développez **Forest PREP**, recherchez un \*\* \<résultat\> \*\* d’exécution réussie à la fin de chaque tâche pour vérifier que la préparation de la forêt s’est déroulée correctement, fermez le journal, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="142ac-116">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="142ac-117">Attendez la fin de la réplication Active Directory ou forcez la réplication vers tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **sites et services Active Directory** pour le contrôleur de domaine racine de la forêt avant d’exécuter la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="142ac-117">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="142ac-118">Forcez la réplication entre les contrôleurs de domaine dans tous les sites Active Directory pour que la réplication au sein des sites se produise en quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="142ac-118">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="142ac-119">Pour utiliser des applets de cmdlet pour préparer la forêt</span><span class="sxs-lookup"><span data-stu-id="142ac-119">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="142ac-120">Ouvrez une session sur un ordinateur qui est joint à un domaine en tant que membre du groupe Domain Admins dans le domaine racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="142ac-120">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="142ac-121">Installez les composants principaux de Lync Server comme suit:</span><span class="sxs-lookup"><span data-stu-id="142ac-121">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="142ac-122">À partir du dossier d’installation ou du média de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="142ac-122">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="142ac-123">Si vous êtes invité à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="142ac-123">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="142ac-124">La boîte de dialogue de configuration de Lync Server 2013 vous invite à entrer un emplacement d’installation des fichiers du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="142ac-124">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="142ac-125">Choisissez l’emplacement par défaut \*\*\*\* ou naviguez jusqu’à l’emplacement de votre choix, puis cliquez sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="142ac-125">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="142ac-126">Sur la page contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="142ac-126">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="142ac-127">Le programme d’installation installe les composants principaux de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="142ac-127">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="142ac-128">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="142ac-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="142ac-129">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="142ac-129">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="142ac-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="142ac-130">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="142ac-131">Si vous ne spécifiez pas le paramètre GroupDomain, la valeur par défaut est le domaine local.</span><span class="sxs-lookup"><span data-stu-id="142ac-131">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span> <span data-ttu-id="142ac-132">Si des groupes universels ont été créés auparavant dans un domaine qui n’est pas le domaine par défaut, vous devez spécifier le paramètre GroupDomain explicitement.</span><span class="sxs-lookup"><span data-stu-id="142ac-132">If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="142ac-133">Attendez la fin de la réplication Active Directory ou forcez la réplication vers tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **sites et services Active Directory** pour le contrôleur de domaine racine de la forêt avant d’exécuter la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="142ac-133">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="142ac-134">Vérifiez que la préparation de la forêt a réussi.</span><span class="sxs-lookup"><span data-stu-id="142ac-134">Verify that forest preparation was successful.</span></span> <span data-ttu-id="142ac-135">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="142ac-135">Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="142ac-136">Cette applet de cmdlet renvoie une valeur de la **LC\_\_FORESTSETTINGS état\_Ready** si la préparation de la forêt a réussi.</span><span class="sxs-lookup"><span data-stu-id="142ac-136">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="142ac-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="142ac-137">See Also</span></span>


[<span data-ttu-id="142ac-138">Utilisation des commandes d’applet pour inverser la préparation d’une forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="142ac-138">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="142ac-139">Préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="142ac-139">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

