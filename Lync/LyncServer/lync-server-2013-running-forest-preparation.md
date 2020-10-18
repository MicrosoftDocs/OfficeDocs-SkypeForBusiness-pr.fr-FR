---
title: 'Lync Server 2013 : exécution de la préparation de la forêt'
description: 'Lync Server 2013 : exécution de la préparation de la forêt.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad3ef2d7583d541701d6606946ca1df1bbd8cf23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577760"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="c99ea-103">Exécution de la préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c99ea-103">Running forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c99ea-104">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="c99ea-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="c99ea-105">Vous pouvez utiliser le programme d’installation ou les applets de commande Lync Server Management Shell pour préparer la forêt.</span><span class="sxs-lookup"><span data-stu-id="c99ea-105">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="c99ea-106">L’applet de commande qui prépare la forêt est **Enable-CsAdForest**.</span><span class="sxs-lookup"><span data-stu-id="c99ea-106">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="c99ea-107">Après avoir préparé la forêt, vous devez vérifier que les paramètres globaux ont été répliqués avant de préparer le domaine.</span><span class="sxs-lookup"><span data-stu-id="c99ea-107">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="c99ea-108">Pour utiliser le programme d’installation afin de préparer la forêt</span><span class="sxs-lookup"><span data-stu-id="c99ea-108">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="c99ea-109">Ouvrez une session sur un ordinateur lié à un domaine en tant que membre du groupe Administrateurs d’entreprise pour le domaine racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="c99ea-109">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="c99ea-110">À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup.exe pour démarrer l’Assistant déploiement.</span><span class="sxs-lookup"><span data-stu-id="c99ea-110">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="c99ea-111">Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.</span><span class="sxs-lookup"><span data-stu-id="c99ea-111">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="c99ea-112">À l’**Étape 3 : Préparer la forêt actuelle**, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c99ea-112">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="c99ea-113">Dans la page **Préparer la forêt**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c99ea-113">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c99ea-114">La préparation de la forêt vous permet de choisir où placer les groupes universels pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c99ea-114">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="c99ea-115">Choisissez un emplacement cohérent avec les conditions requises de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c99ea-115">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="c99ea-116">Sur la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="c99ea-116">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="c99ea-117">Sous la colonne **action** , développez préparation de la **forêt**, recherchez le **\<Success\>** résultat d’exécution à la fin de chaque tâche pour vérifier que la préparation de la forêt s’est correctement effectuée, fermez le journal, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="c99ea-117">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="c99ea-p103">Attendez que la réplication Active Directory soit terminée ou forcez la réplication sur tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **Sites et services Active Directory** pour le contrôleur du domaine racine de la forêt, avant d’exécuter l’opération de préparation d’un domaine. Forcez la réplication entre les contrôleurs de domaine sur tous les sites Active Directory pour faire en sorte que la réplication au sein de ces sites se produise en quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="c99ea-p103">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation. Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="c99ea-120">Pour préparer la forêt à l’aide d’applets de commande</span><span class="sxs-lookup"><span data-stu-id="c99ea-120">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="c99ea-121">Ouvrez une session sur un ordinateur qui est associé à un domaine en tant que membre du groupe Administrateurs du domaine dans le domaine racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="c99ea-121">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="c99ea-122">Installez les composants principaux de Lync Server comme suit :</span><span class="sxs-lookup"><span data-stu-id="c99ea-122">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="c99ea-123">À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup.exe pour démarrer l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c99ea-123">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="c99ea-124">Si le système vous invite à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="c99ea-124">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="c99ea-125">La boîte de dialogue Configuration de Lync Server 2013 vous invite à indiquer un emplacement d’installation des fichiers Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c99ea-125">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="c99ea-126">Choisissez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder à un emplacement de votre choix, puis cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="c99ea-126">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="c99ea-127">Dans la page Contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c99ea-127">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="c99ea-128">Le programme d’installation installe les composants principaux de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c99ea-128">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="c99ea-129">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c99ea-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="c99ea-130">Générer</span><span class="sxs-lookup"><span data-stu-id="c99ea-130">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="c99ea-131">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c99ea-131">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="c99ea-p106">Si vous omettez le paramètre GroupDomain, le domaine local est utilisé par défaut. Si les groupes universels ont été créés dans un domaine qui n’est pas le domaine par défaut, vous devez spécifier explicitement le paramètre GroupDomain.</span><span class="sxs-lookup"><span data-stu-id="c99ea-p106">If you do not specify the GroupDomain parameter, the default value is the local domain. If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="c99ea-134">Attendez que la réplication Active Directory soit terminée ou forcez la réplication sur tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **Sites et services Active Directory** pour le contrôleur du domaine racine de la forêt, avant d’exécuter l’opération de préparation d’un domaine.</span><span class="sxs-lookup"><span data-stu-id="c99ea-134">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="c99ea-p107">Vérifiez que la préparation de la forêt a été exécutée avec succès. Exécutez :</span><span class="sxs-lookup"><span data-stu-id="c99ea-p107">Verify that forest preparation was successful. Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="c99ea-137">Cette applet de commande renvoie une valeur de **LC \_ FORESTSETTINGS \_ State \_ Ready** si la préparation de la forêt a réussi.</span><span class="sxs-lookup"><span data-stu-id="c99ea-137">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c99ea-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c99ea-138">See Also</span></span>


[<span data-ttu-id="c99ea-139">Utilisation d’applets de commande pour inverser la préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c99ea-139">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="c99ea-140">Préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c99ea-140">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

