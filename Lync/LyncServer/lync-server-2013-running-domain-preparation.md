---
title: 'Lync Server 2013 : Exécution de la préparation du domaine'
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
ms.openlocfilehash: 408dea780b4136f86ffed30d199d1d0ee63d6821
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="f678d-102">Exécution de la préparation du domaine pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f678d-102">Running domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f678d-103">_**Dernière modification de la rubrique :** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="f678d-103">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="f678d-104">Vous pouvez utiliser les applets de applet de configuration ou Lync Server Management Shell pour préparer les domaines.</span><span class="sxs-lookup"><span data-stu-id="f678d-104">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="f678d-105">L’applet de cmdlet qui prépare un domaine est **Enable-CsAdDomain**.</span><span class="sxs-lookup"><span data-stu-id="f678d-105">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="f678d-106">La préparation du domaine est l’étape finale de la préparation des services de domaine Active Directory pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f678d-106">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="f678d-107">Pour préparer le domaine à l’aide du programme d’installation</span><span class="sxs-lookup"><span data-stu-id="f678d-107">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="f678d-108">Ouvrez une session sur n’importe quel serveur du domaine en tant que membre du groupe Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="f678d-108">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="f678d-109">À partir du dossier d’installation ou du média de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f678d-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="f678d-110">Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.</span><span class="sxs-lookup"><span data-stu-id="f678d-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="f678d-111">À l’**Étape 5 : Préparer le domaine actuel**, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f678d-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="f678d-112">Dans la page **préparer le domaine** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f678d-112">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="f678d-113">Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="f678d-113">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="f678d-114">Dans la colonne **action** , développez **Domain PREP**, recherchez un \*\* \<résultat\> \*\* d’exécution réussie à la fin de chaque tâche pour vérifier que la préparation du domaine s’est déroulée correctement, fermez le journal, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f678d-114">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="f678d-115">Attendez la fin de la réplication Active Directory pour qu’elle soit terminée ou forcée de réplication à tous les contrôleurs de domaine figurant dans le composant logiciel enfichable sites et services Active Directory pour le contrôleur de domaine racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="f678d-115">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="f678d-116">Pour utiliser des applets de cmdlet pour préparer le domaine</span><span class="sxs-lookup"><span data-stu-id="f678d-116">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="f678d-117">Ouvrez une session sur n’importe quel serveur du domaine en tant que membre du groupe Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="f678d-117">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="f678d-118">Installez les composants principaux de Lync Server comme suit :</span><span class="sxs-lookup"><span data-stu-id="f678d-118">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="f678d-119">À partir du dossier d’installation ou du média de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f678d-119">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="f678d-120">Si vous êtes invité à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f678d-120">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="f678d-121">La boîte de dialogue de configuration de Lync Server 2013 vous invite à entrer un emplacement d’installation des fichiers du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="f678d-121">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="f678d-122">Choisissez l’emplacement par défaut ou **Naviguez** jusqu’à l’emplacement de votre choix, puis cliquez sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="f678d-122">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="f678d-123">Sur la page contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f678d-123">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="f678d-124">Le programme d’installation installe les composants principaux de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f678d-124">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="f678d-125">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f678d-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="f678d-126">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="f678d-126">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="f678d-127">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f678d-127">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="f678d-128">Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le Domain local.</span><span class="sxs-lookup"><span data-stu-id="f678d-128">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="f678d-129">Vérifiez que la préparation du domaine a réussi.</span><span class="sxs-lookup"><span data-stu-id="f678d-129">Verify that domain preparation was successful.</span></span> <span data-ttu-id="f678d-130">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="f678d-130">Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="f678d-131">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f678d-131">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f678d-132">Le paramètre GlobalSettingsDomainController vous permet d’indiquer l’emplacement de stockage des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="f678d-132">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="f678d-133">Si vos paramètres sont stockés dans le conteneur système (qui est courant pour les déploiements de mise à niveau qui n’ont pas été migrés vers le conteneur de configuration), vous définissez un contrôleur de domaine à la racine de votre forêt Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f678d-133">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="f678d-134">Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous devez définir un contrôleur de domaine dans la forêt.</span><span class="sxs-lookup"><span data-stu-id="f678d-134">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="f678d-135">Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et font référence à tout&nbsp;contrôleur de domaine dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="f678d-135">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="f678d-136">Si vous ne spécifiez pas le paramètre **Domain** , la valeur par défaut est le Domain local.</span><span class="sxs-lookup"><span data-stu-id="f678d-136">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="f678d-137">Cette applet de cmdlet renvoie une valeur de la fonction **\_DOMAINSETTINGS\_\_**</span><span class="sxs-lookup"><span data-stu-id="f678d-137">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f678d-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f678d-138">See Also</span></span>


[<span data-ttu-id="f678d-139">Utilisation d’applets de commande pour inverser la préparation d’un domaine pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f678d-139">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="f678d-140">Préparation des domaines pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f678d-140">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

