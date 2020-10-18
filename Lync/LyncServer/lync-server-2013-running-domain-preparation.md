---
title: 'Lync Server 2013 : exécution de la préparation du domaine'
description: 'Lync Server 2013 : exécution de la préparation du domaine.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f2c4ebe94d07ed2d1fd9be013cd8e88204312f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577780"
---
# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="49c17-103">Exécution de la préparation du domaine pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49c17-103">Running domain preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49c17-104">_**Dernière modification de la rubrique :** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="49c17-104">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="49c17-105">Vous pouvez utiliser le programme d’installation ou les applets de commande Lync Server Management Shell pour préparer les domaines.</span><span class="sxs-lookup"><span data-stu-id="49c17-105">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="49c17-106">L’applet de commande qui prépare un domaine est **Enable-CsAdDomain**.</span><span class="sxs-lookup"><span data-stu-id="49c17-106">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="49c17-107">La préparation du domaine est la dernière étape de la préparation des services de domaine Active Directory pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49c17-107">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="49c17-108">Pour préparer les domaines à l’aide du programme d’installation</span><span class="sxs-lookup"><span data-stu-id="49c17-108">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="49c17-109">Ouvrez une session sur un serveur dans le domaine en tant que membre du groupe Administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="49c17-109">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="49c17-110">À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup.exe pour démarrer l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49c17-110">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="49c17-111">Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.</span><span class="sxs-lookup"><span data-stu-id="49c17-111">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="49c17-112">À l’**Étape 5 : Préparer le domaine actuel**, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="49c17-112">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="49c17-113">Sur la page **préparer le domaine** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="49c17-113">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="49c17-114">Sur la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="49c17-114">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="49c17-115">Sous la colonne **action** , développez **préparation du domaine**, recherchez un résultat d' **\<Success\>** exécution à la fin de chaque tâche pour vérifier que la préparation du domaine s’est correctement effectuée, fermez le journal, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="49c17-115">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="49c17-116">Attendez que la réplication Active Directory soit terminée ou forcez la réplication sur tous les contrôleurs de domaine figurant dans le composant logiciel enfichable sites et services Active Directory pour le contrôleur de domaine racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="49c17-116">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="49c17-117">Pour préparer le domaine à l’aide de cmdlets</span><span class="sxs-lookup"><span data-stu-id="49c17-117">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="49c17-118">Ouvrez une session sur un serveur dans le domaine en tant que membre du groupe Administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="49c17-118">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="49c17-119">Installez les composants principaux de Lync Server comme suit :</span><span class="sxs-lookup"><span data-stu-id="49c17-119">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="49c17-120">À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup.exe pour démarrer l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49c17-120">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="49c17-121">Si le système vous invite à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="49c17-121">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="49c17-122">La boîte de dialogue Configuration de Lync Server 2013 vous invite à indiquer un emplacement d’installation des fichiers Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49c17-122">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="49c17-123">Choisissez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder à un emplacement de votre choix, puis cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="49c17-123">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="49c17-124">Dans la page Contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="49c17-124">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="49c17-125">Le programme d’installation installe les composants principaux de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49c17-125">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="49c17-126">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="49c17-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="49c17-127">Générer</span><span class="sxs-lookup"><span data-stu-id="49c17-127">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="49c17-128">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="49c17-128">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="49c17-129">Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="49c17-129">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="49c17-130">Vérifiez que la préparation du domaine a réussi.</span><span class="sxs-lookup"><span data-stu-id="49c17-130">Verify that domain preparation was successful.</span></span> <span data-ttu-id="49c17-131">Générer</span><span class="sxs-lookup"><span data-stu-id="49c17-131">Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="49c17-132">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="49c17-132">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="49c17-133">Le paramètre GlobalSettingsDomainController vous permet d'indiquer où sont stockés les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="49c17-133">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="49c17-134">Si vos paramètres sont stockés dans le conteneur système (ce qui est normal dans les déploiements de mise à niveau dont les paramètres globaux n’ont pas été migrés vers le conteneur de configuration), vous définissez un contrôleur de domaine à la racine de votre forêt Active Directory.</span><span class="sxs-lookup"><span data-stu-id="49c17-134">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="49c17-135">Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous définissez tout contrôleur de domaine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="49c17-135">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="49c17-136">Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et font référence à n’importe quel contrôleur de domaine dans AD &nbsp; DS.</span><span class="sxs-lookup"><span data-stu-id="49c17-136">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="49c17-137">Si vous ne spécifiez pas le paramètre **Domain** , la valeur par défaut est le domaine local.</span><span class="sxs-lookup"><span data-stu-id="49c17-137">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="49c17-138">Cette applet de commande renvoie une valeur de **LC \_ DOMAINSETTINGS \_ State \_ Ready** si la préparation du domaine a réussi.</span><span class="sxs-lookup"><span data-stu-id="49c17-138">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49c17-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="49c17-139">See Also</span></span>


[<span data-ttu-id="49c17-140">Utilisation d’applets de commande pour inverser la préparation du domaine pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49c17-140">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="49c17-141">Préparation des domaines pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49c17-141">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

