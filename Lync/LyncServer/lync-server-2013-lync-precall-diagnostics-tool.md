---
title: 'Lync Server 2013 : outil de diagnostic de préappel Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79009ce890e37e7238e3fef18f719fb3da411889
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="aba0f-102">Outil de diagnostic de préappel Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aba0f-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aba0f-103">_**Dernière modification de la rubrique :** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="aba0f-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="aba0f-104">L’outil Lync precall Diagnostics (PCD) est une application cliente qui vous permet de voir comment l’état actuel de votre réseau peut avoir un impact sur la qualité audio dans un appel vocal à venir.</span><span class="sxs-lookup"><span data-stu-id="aba0f-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="aba0f-105">PCD est très utile dans les situations où le dernier tronçon d’un réseau est probablement le plus faible (par exemple, avec des ordinateurs portables sur un réseau WiFi public ou des particuliers).</span><span class="sxs-lookup"><span data-stu-id="aba0f-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="aba0f-106">PCD crée un petit flux de paquets qui traverse cette branche finale du réseau.</span><span class="sxs-lookup"><span data-stu-id="aba0f-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="aba0f-107">L’outil analyse ensuite le flux de paquets pour estimer comment la gigue et la perte le long de cette jambe peuvent influer sur la qualité de l’appel, puis fournit un rapport.</span><span class="sxs-lookup"><span data-stu-id="aba0f-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="aba0f-108">Vous pouvez exécuter PCD en continu sur le client, même lorsque des appels sont en cours.</span><span class="sxs-lookup"><span data-stu-id="aba0f-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="aba0f-109">Le flux de paquets n’a pas d’impact significatif sur la bande passante.</span><span class="sxs-lookup"><span data-stu-id="aba0f-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="aba0f-110">**La dernière version du PCD, version 1,1, inclut les améliorations suivantes :**</span><span class="sxs-lookup"><span data-stu-id="aba0f-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="aba0f-111">Prendre en charge des mots de passe plus longs, qui peuvent désormais contenir jusqu’à 127 caractères</span><span class="sxs-lookup"><span data-stu-id="aba0f-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="aba0f-112">Diagnostics supplémentaires pour les problèmes de connexion à l’authentification</span><span class="sxs-lookup"><span data-stu-id="aba0f-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="aba0f-113">Meilleure prise en charge des déploiements hybrides Lync</span><span class="sxs-lookup"><span data-stu-id="aba0f-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="aba0f-114">Mises à jour du sélecteur d’informations d’identification</span><span class="sxs-lookup"><span data-stu-id="aba0f-114">Updates to credential picker</span></span>

  - <span data-ttu-id="aba0f-115">Améliorations de la stabilité</span><span class="sxs-lookup"><span data-stu-id="aba0f-115">Stability improvements</span></span>

<span data-ttu-id="aba0f-116">Nous apprécions tout commentaire.</span><span class="sxs-lookup"><span data-stu-id="aba0f-116">We appreciate any feedback.</span></span> <span data-ttu-id="aba0f-117">Veuillez envoyer toutes les questions d’assistance ou tous les problèmes à l' <pcdfb@microsoft.com>alias de [Commentaire PCD](mailto:pcdfb@microsoft.com) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="aba0f-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="aba0f-118">Cette rubrique comprend les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="aba0f-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="aba0f-119">Versions de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="aba0f-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="aba0f-120">Configuration requise pour Lync PCD</span><span class="sxs-lookup"><span data-stu-id="aba0f-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="aba0f-121">Fonctionnalités de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="aba0f-121">Lync PCD Features</span></span>

  - <span data-ttu-id="aba0f-122">Exécution de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="aba0f-122">Running Lync PCD</span></span>

  - <span data-ttu-id="aba0f-123">Désinstallation de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="aba0f-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="aba0f-124">Versions de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="aba0f-124">Lync PCD Versions</span></span>

<span data-ttu-id="aba0f-125">Cette rubrique décrit les versions suivantes de l’outil, disponibles en téléchargement gratuit :</span><span class="sxs-lookup"><span data-stu-id="aba0f-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="aba0f-126">Application de bureau Windows[https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914)()</span><span class="sxs-lookup"><span data-stu-id="aba0f-126">Windows Desktop App ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="aba0f-127">Configuration requise pour Lync PCD</span><span class="sxs-lookup"><span data-stu-id="aba0f-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aba0f-128">PCD nécessite l’installation et la configuration de l’API Web Unified Communications (UCWA) pour prendre en charge les clients mobiles dans le déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aba0f-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="aba0f-129">UCWA est installé avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aba0f-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="aba0f-130">Configuration requise pour les applications de bureau Windows</span><span class="sxs-lookup"><span data-stu-id="aba0f-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="aba0f-131">N’importe quelle édition du système d’exploitation Windows 7 ou Windows 8</span><span class="sxs-lookup"><span data-stu-id="aba0f-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="aba0f-132">Microsoft .NET Framework 4,5 disponible sur[https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="aba0f-132">Microsoft .NET Framework 4.5 available at [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="aba0f-133">Fonctionnalités de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="aba0f-133">Lync PCD Features</span></span>

<span data-ttu-id="aba0f-134">Lync PCD inclut les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="aba0f-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="aba0f-135">Exécution par défaut à la demande (rafales de 2 minutes)</span><span class="sxs-lookup"><span data-stu-id="aba0f-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="aba0f-136">Mode de fonctionnement toujours activé (jusqu’à 24 heures en mode alignement)</span><span class="sxs-lookup"><span data-stu-id="aba0f-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="aba0f-137">Vue historique de vos séries de tests</span><span class="sxs-lookup"><span data-stu-id="aba0f-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="aba0f-138">Diagnostiquer les échecs de connexion (Lync PCD pour Windows 8 uniquement)</span><span class="sxs-lookup"><span data-stu-id="aba0f-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="aba0f-139">![Capture d’écran de connexion des fonctionnalités Lync PCD](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Capture d’écran de connexion des fonctionnalités Lync PCD")</span><span class="sxs-lookup"><span data-stu-id="aba0f-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="aba0f-140">Vue graphique des mesures réseau : MOS réseau, perte de paquets et gigue d’interarrivée en mode plein écran et en mode d’affichage ancré.</span><span class="sxs-lookup"><span data-stu-id="aba0f-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="aba0f-141">**Affichage plein écran**</span><span class="sxs-lookup"><span data-stu-id="aba0f-141">**Full screen view**</span></span>

<span data-ttu-id="aba0f-142">![Graphiques de résultats de test de l’outil de diagnostic d’avant-appel](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Graphiques de résultats de test de l’outil de diagnostic d’avant-appel")</span><span class="sxs-lookup"><span data-stu-id="aba0f-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="aba0f-143">**Vue aimantée**</span><span class="sxs-lookup"><span data-stu-id="aba0f-143">**Snapped view**</span></span>

<span data-ttu-id="aba0f-144">![Résultats du test d’utilisation de l’outil de diagnostic d’avant-appel](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Résultats du test d’utilisation de l’outil de diagnostic d’avant-appel")</span><span class="sxs-lookup"><span data-stu-id="aba0f-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="aba0f-145">Exécution de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="aba0f-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="aba0f-146">Exécution de l’application de bureau Windows</span><span class="sxs-lookup"><span data-stu-id="aba0f-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="aba0f-147">Pour démarrer le PCD sur un système Windows 7, sélectionnez **Précall Diagnostics** dans le menu **Démarrer** .</span><span class="sxs-lookup"><span data-stu-id="aba0f-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="aba0f-148">Pour démarrer le PCD sur un système Windows 8, sélectionnez l’icône sur votre écran de démarrage, ou recherchez « préappels Diagnostics ».</span><span class="sxs-lookup"><span data-stu-id="aba0f-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="aba0f-149">![Icône de l’outil de diagnostic d’avant-appel](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icône de l’outil de diagnostic d’avant-appel")</span><span class="sxs-lookup"><span data-stu-id="aba0f-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="aba0f-150">Lorsque l’outil démarre, sélectionnez la méthode de votre choix pour fournir les informations d’identification et sélectionnez le mode de fonctionnement réseau dans la boîte de dialogue Options de l' **outil de diagnostic** de l’avant-appel, puis cliquez sur **OK**:</span><span class="sxs-lookup"><span data-stu-id="aba0f-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="aba0f-151">Sélectionnez le bouton **Démarrer le test** pour commencer à exécuter les Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="aba0f-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="aba0f-152">Si vous avez sélectionné l’option **utiliser les informations d’identification réseau** , le test commence immédiatement.</span><span class="sxs-lookup"><span data-stu-id="aba0f-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="aba0f-153">Si vous avez sélectionné l’option **me laisser entrer des informations d’identification** , la boîte de dialogue **sécurité de Windows** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="aba0f-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="aba0f-154">Une fois que vous avez entré vos informations d’identification, le test démarre.</span><span class="sxs-lookup"><span data-stu-id="aba0f-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="aba0f-155">Désinstallation de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="aba0f-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="aba0f-156">Pour supprimer Lync PCD, suivez la procédure correspondant à votre système d’exploitation :</span><span class="sxs-lookup"><span data-stu-id="aba0f-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="aba0f-157">Sur un système Windows 7, ouvrez le **panneau de configuration**, sélectionnez **programmes et fonctionnalités**, puis double-cliquez sur **Lync 2013 precall Diagnostics**.</span><span class="sxs-lookup"><span data-stu-id="aba0f-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="aba0f-158">Sur un système Windows 8, cliquez avec le bouton droit sur la vignette PCD, puis cliquez sur **désinstaller** dans la barre de l’application en bas de l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="aba0f-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

