---
title: Migration des paramètres d’application de parcage d’appel
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee1afd2e53bd29571818b9194fe77d3d350386f1
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="df5a3-102">Migration des paramètres d’application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="df5a3-102">Migrate Call Park application settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df5a3-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="df5a3-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="df5a3-104">La migration de l’application de parc d’appels de Lync Server 2010 vers Lync Server 2013 inclut la mise en service du pool Lync Server 2013 avec n’importe quel morceau de musique personnalisé sur les fichiers qui ont été téléchargés dans Lync Server 2010, en restaurant les paramètres de niveau de service et en reciblant le stationnement des appels vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df5a3-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="df5a3-105">Si des fichiers personnalisés de musique en attente ont été configurés dans le pool Lync Server 2010, ces fichiers doivent être copiés vers le nouveau pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df5a3-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="df5a3-106">Par ailleurs, il est recommandé de sauvegarder les fichiers de conservation de musique personnalisés de Lync Server 2010 vers une autre destination pour conserver une copie de sauvegarde distincte de tous les fichiers de mise en attente personnalisés qui ont été téléchargés pour le parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="df5a3-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="df5a3-107">Les fichiers de conservation de musique personnalisés pour l’application de parc d’appels sont stockés dans le magasin de fichiers du pool.</span><span class="sxs-lookup"><span data-stu-id="df5a3-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="df5a3-108">Pour copier les fichiers audio à partir d’un magasin de fichiers du pool Lync Server 2010 dans un magasin de fichiers 2013 Server, utilisez la commande **xcopy** avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="df5a3-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="df5a3-109">Lorsque tous les fichiers audio personnalisés ont été copiés sur le magasin de fichiers 2013 Lync Server, les paramètres de l’application de parc d’appels du pool Lync Server 2013 doivent être configurés et les plages d’orbites du parc d’appels associées au pool Lync Server 2010 doivent être réaffectées à le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df5a3-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="df5a3-110">Les paramètres de l’application de parc d’appels incluent le seuil de délai de capture, l’activation ou la désactivation de la musique en attente, le nombre maximal de tentatives de sélection d’appels et la demande d’expiration.</span><span class="sxs-lookup"><span data-stu-id="df5a3-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="df5a3-111">Vous devez gérer les paramètres de l’application parc d’appels à l’aide de Lync Server Management Shell pour exécuter l’applet de demande **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="df5a3-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="df5a3-112">Vous ne pouvez pas gérer les paramètres de l’application parc d’appels à l’aide du panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df5a3-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="df5a3-113">**Reconfigurer les paramètres du service de parc d’appels**</span><span class="sxs-lookup"><span data-stu-id="df5a3-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="df5a3-114">À partir du serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="df5a3-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="df5a3-115">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="df5a3-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="df5a3-116">Si les paramètres de l’application de parc d’appels Lync Server 2013 sont identiques à ceux de l’ancienne génération de Lync Server 2010, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="df5a3-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="df5a3-117">Si les paramètres d’application de parc d’appels sont différents pour les environnements Lync Server 2013 et Lync Server 2010, utilisez l’applet de cmdlet ci-dessous en tant que modèle pour mettre à jour ces modifications.</span><span class="sxs-lookup"><span data-stu-id="df5a3-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="df5a3-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold"<LS2010 CPS TimeSpan>"-EnableMusicOnHold"<LS2010 CPS value>"-MaxCallPickupAttempts"<LS2010 CPS pickup attempts>"-OnTimeoutURI"<LS2010 CPS timeout URI>"```</span><span class="sxs-lookup"><span data-stu-id="df5a3-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="df5a3-119">Pour réattribuer toutes les plages d’orbites du parc d’appels du pool Lync Server 2010 au pool Lync Server 2013, vous pouvez utiliser le panneau de configuration de Lync Server ou Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="df5a3-119">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="df5a3-120">**Réaffecter toutes les plages d’orbites du parc d’appels à l’aide du panneau de configuration de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="df5a3-120">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="df5a3-121">Ouvrez le Paneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df5a3-121">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="df5a3-122">Dans le volet gauche, sélectionnez **fonctions vocales**.</span><span class="sxs-lookup"><span data-stu-id="df5a3-122">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="df5a3-123">Sélectionnez l’onglet **parc d’appels** .</span><span class="sxs-lookup"><span data-stu-id="df5a3-123">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="df5a3-124">Pour chaque gamme de parking d’appel attribuée à un pool Lync Server 2010, modifiez le paramètre **de nom de domaine complet du serveur de destination** et sélectionnez le pool lync Server 2013 qui traitera les demandes de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="df5a3-124">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="df5a3-125">Sélectionnez **valider** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="df5a3-125">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="df5a3-126">**Réaffecter toutes les plages d’orbites du parc d’appels à l’aide de Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="df5a3-126">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="df5a3-127">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="df5a3-127">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="df5a3-128">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="df5a3-128">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="df5a3-129">Cette cmdlet recense toutes les plages d’orbites du parc d’appels du déploiement.</span><span class="sxs-lookup"><span data-stu-id="df5a3-129">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="df5a3-130">Toutes les orbites du parc d’appels avec les paramètres **CallParkServiceId** et **CallParkServerFqdn** définis comme le pool Lync Server 2010 doivent être réaffectées.</span><span class="sxs-lookup"><span data-stu-id="df5a3-130">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="df5a3-131">Pour réattribuer la plage de la fonction d’appel de l’équipe du parc du serveur 2010 au pool Lync Server 2013, sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="df5a3-131">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="df5a3-132">Après avoir réaffecté toutes les plages d’orbite du parc d’appels au pool Lync Server 2013, le processus de migration de l’application de parc d’appels sera exécuté et le pool Lync Server 2013 traitera toutes les futures demandes de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="df5a3-132">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

