---
title: 'Lync Server 2013: outil Diagnostics pour les préappel Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e22b542a5840714455d4abdb0a7163e6a8ba748
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="36e6a-102">Outil de diagnostics d’préappel Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36e6a-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36e6a-103">_**Dernière modification de la rubrique:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="36e6a-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="36e6a-104">L’outil de diagnostics d’avant-appel Lync (PCD) est une application basée sur le client qui vous permet de voir comment l’état actuel de votre réseau peut avoir un impact sur la qualité audio lors d’un appel voix entreprise à venir.</span><span class="sxs-lookup"><span data-stu-id="36e6a-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="36e6a-105">PCD est particulièrement utile dans les situations dans lesquelles le dernier tronçon d’un réseau est susceptible d’être faible (par exemple, avec des ordinateurs portables sur un réseau WiFi public ou des particuliers).</span><span class="sxs-lookup"><span data-stu-id="36e6a-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="36e6a-106">PCD crée un petit flux de paquets qui traverse ce dernier tronçon du réseau.</span><span class="sxs-lookup"><span data-stu-id="36e6a-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="36e6a-107">L’outil analyse alors le flux de paquets pour évaluer la façon dont la gigue et la perte peuvent avoir un impact sur la qualité des appels, puis fournit un rapport.</span><span class="sxs-lookup"><span data-stu-id="36e6a-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="36e6a-108">Vous pouvez exécuter PCD en continu sur le client, même lorsque les appels sont en train d’être placés.</span><span class="sxs-lookup"><span data-stu-id="36e6a-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="36e6a-109">Le flux de paquets n’a pas d’effet notable sur la bande passante.</span><span class="sxs-lookup"><span data-stu-id="36e6a-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="36e6a-110">**La dernière version du PCD, version 1,1, inclut les améliorations suivantes:**</span><span class="sxs-lookup"><span data-stu-id="36e6a-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="36e6a-111">Prise en charge de mots de passe plus longs, qui peuvent désormais comporter jusqu’à 127 caractères</span><span class="sxs-lookup"><span data-stu-id="36e6a-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="36e6a-112">Diagnostics supplémentaires pour les problèmes de connexion d’authentification</span><span class="sxs-lookup"><span data-stu-id="36e6a-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="36e6a-113">Prise en charge améliorée des déploiements hybrides de Lync</span><span class="sxs-lookup"><span data-stu-id="36e6a-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="36e6a-114">Mises à jour du sélecteur d’informations d’identification</span><span class="sxs-lookup"><span data-stu-id="36e6a-114">Updates to credential picker</span></span>

  - <span data-ttu-id="36e6a-115">Améliorations de la stabilité</span><span class="sxs-lookup"><span data-stu-id="36e6a-115">Stability improvements</span></span>

<span data-ttu-id="36e6a-116">Nous vous remercions de votre avis.</span><span class="sxs-lookup"><span data-stu-id="36e6a-116">We appreciate any feedback.</span></span> <span data-ttu-id="36e6a-117">Vous pouvez envoyer toutes vos questions ou problèmes d’assistance à l’alias <pcdfb@microsoft.com>de [Commentaires PCD](mailto:pcdfb@microsoft.com) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="36e6a-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="36e6a-118">Cette rubrique inclut les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="36e6a-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="36e6a-119">Versions de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="36e6a-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="36e6a-120">Configuration système requise pour Lync PCD</span><span class="sxs-lookup"><span data-stu-id="36e6a-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="36e6a-121">Fonctionnalités de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="36e6a-121">Lync PCD Features</span></span>

  - <span data-ttu-id="36e6a-122">Exécution de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="36e6a-122">Running Lync PCD</span></span>

  - <span data-ttu-id="36e6a-123">Désinstallation de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="36e6a-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="36e6a-124">Versions de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="36e6a-124">Lync PCD Versions</span></span>

<span data-ttu-id="36e6a-125">Cette rubrique décrit les versions suivantes de l’outil disponibles en téléchargement gratuit:</span><span class="sxs-lookup"><span data-stu-id="36e6a-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="36e6a-126">Application de bureau Windows[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)()</span><span class="sxs-lookup"><span data-stu-id="36e6a-126">Windows Desktop App ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="36e6a-127">Configuration système requise pour Lync PCD</span><span class="sxs-lookup"><span data-stu-id="36e6a-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36e6a-128">PCD nécessite l’installation et la configuration de l’API Web de communications unifiées (UCWA) pour la prise en charge des clients mobiles dans le déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="36e6a-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="36e6a-129">UCWA est installé avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="36e6a-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="36e6a-130">Configuration requise pour l’application de bureau Windows</span><span class="sxs-lookup"><span data-stu-id="36e6a-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="36e6a-131">Toute édition du système d’exploitation Windows 7 ou Windows 8</span><span class="sxs-lookup"><span data-stu-id="36e6a-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="36e6a-132">Microsoft .NET Framework 4,5 disponible sur le[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="36e6a-132">Microsoft .NET Framework 4.5 available at [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="36e6a-133">Fonctionnalités de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="36e6a-133">Lync PCD Features</span></span>

<span data-ttu-id="36e6a-134">Lync PCD inclut les fonctionnalités suivantes:</span><span class="sxs-lookup"><span data-stu-id="36e6a-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="36e6a-135">Exécution par défaut à la demande (burst de 2 minutes)</span><span class="sxs-lookup"><span data-stu-id="36e6a-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="36e6a-136">Exécution dans le mode toujours activé (jusqu’à 24 heures dans l’affichage aligné)</span><span class="sxs-lookup"><span data-stu-id="36e6a-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="36e6a-137">Affichage historique de vos séries de tests</span><span class="sxs-lookup"><span data-stu-id="36e6a-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="36e6a-138">Diagnostiquer les échecs de connexion (Lync PCD pour Windows 8 uniquement)</span><span class="sxs-lookup"><span data-stu-id="36e6a-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="36e6a-139">![Capture d’écran de la capture d’écran de l’application Lync] (images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Capture d’écran de la capture d’écran de l’application Lync")</span><span class="sxs-lookup"><span data-stu-id="36e6a-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="36e6a-140">Affichage graphique des métriques du réseau (MOS du réseau, perte de paquets et gigue d’interentrée) en plein écran et en affichage aligné.</span><span class="sxs-lookup"><span data-stu-id="36e6a-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="36e6a-141">**Mode plein écran**</span><span class="sxs-lookup"><span data-stu-id="36e6a-141">**Full screen view**</span></span>

<span data-ttu-id="36e6a-142">Graphes de résultats de test de l' ![outil de diagnostic avant appel] Graphes de résultats de test de l' (images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "outil de diagnostic avant appel")</span><span class="sxs-lookup"><span data-stu-id="36e6a-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="36e6a-143">**Affichage aligné**</span><span class="sxs-lookup"><span data-stu-id="36e6a-143">**Snapped view**</span></span>

<span data-ttu-id="36e6a-144">![Résultats du test d’utilisation de l’outil de diagnostic avant appel] (images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Résultats du test d’utilisation de l’outil de diagnostic avant appel")</span><span class="sxs-lookup"><span data-stu-id="36e6a-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="36e6a-145">Exécution de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="36e6a-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="36e6a-146">Exécution d’une application de bureau Windows</span><span class="sxs-lookup"><span data-stu-id="36e6a-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="36e6a-147">Pour démarrer le PCD sur un système Windows 7, sélectionnez **Diagnostics préappel** dans le menu **Démarrer** .</span><span class="sxs-lookup"><span data-stu-id="36e6a-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="36e6a-148">Pour démarrer le PCD sur un système Windows 8, sélectionnez l’icône sur votre écran d’accueil, ou recherchez «Diagnostics de préappel».</span><span class="sxs-lookup"><span data-stu-id="36e6a-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="36e6a-149">![Icône] de l’outil de diagnostic préappel (images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icône") de l’outil de diagnostic préappel</span><span class="sxs-lookup"><span data-stu-id="36e6a-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="36e6a-150">Lorsque l’outil démarre, sélectionnez la méthode de votre choix pour fournir des informations d’identification, puis sélectionnez le mode de fonctionnement réseau dans la boîte de dialogue Options de l' **outil Diagnostics** de l’appel, puis cliquez sur **OK**:</span><span class="sxs-lookup"><span data-stu-id="36e6a-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="36e6a-151">Cliquez sur le bouton **Démarrer le test** pour démarrer l’exécution des Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="36e6a-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="36e6a-152">Si vous avez sélectionné l’option **utiliser les informations d’identification réseau** , le test commence immédiatement.</span><span class="sxs-lookup"><span data-stu-id="36e6a-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="36e6a-153">Si vous avez sélectionné l’option **me permettre d’entrer mes informations d’identification** , la boîte de dialogue de **sécurité Windows** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="36e6a-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="36e6a-154">Après avoir entré vos informations d’identification, le test démarre.</span><span class="sxs-lookup"><span data-stu-id="36e6a-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="36e6a-155">Désinstallation de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="36e6a-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="36e6a-156">Pour supprimer Lync PCD, suivez la procédure pour votre système d’exploitation:</span><span class="sxs-lookup"><span data-stu-id="36e6a-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="36e6a-157">Sur un système Windows 7, ouvrez le **panneau de configuration**, sélectionnez **programmes et fonctionnalités**, puis double-cliquez sur Diagnostics de l' **appel Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="36e6a-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="36e6a-158">Sur un système Windows 8, cliquez avec le bouton droit sur la vignette PCD \*\*\*\* , puis cliquez sur désinstaller dans la barre de l’application en bas de l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="36e6a-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

