---
title: Migration des paramètres d’application de parcage d’appel
description: Migrer les paramètres d’application de parcage d’appel.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da90ca4ee4dd53451c29b8c39861dc76a17ca3c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579410"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="a4448-103">Migration des paramètres d’application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="a4448-103">Migrate Call Park application settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4448-104">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a4448-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a4448-105">La migration de l’application de parcage d’appel de Lync Server 2010 vers Lync Server 2013 inclut la mise en service du pool Lync Server 2013 avec des fichiers de mise en attente musicaux personnalisés qui ont été téléchargés dans Lync Server 2010, la restauration des paramètres de niveau de service et le reciblage de toutes les orbites de parcage d’appel vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4448-105">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="a4448-106">Si des fichiers de mise en attente musicale personnalisés ont été configurés dans le pool Lync Server 2010, ces fichiers doivent être copiés dans le nouveau pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4448-106">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="a4448-107">De plus, il est recommandé de sauvegarder tous les fichiers de mise en attente musicale personnalisés de Lync Server 2010 vers une autre destination afin de conserver une copie de sauvegarde distincte des fichiers musicaux en attente personnalisés qui ont été téléchargés pour le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="a4448-107">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="a4448-108">Les fichiers d’attente musicale personnalisée de l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool.</span><span class="sxs-lookup"><span data-stu-id="a4448-108">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="a4448-109">Pour copier les fichiers audio à partir d’un magasin de fichiers de pool Lync Server 2010 vers un magasin de fichiers Lync Server 2013, utilisez la commande **xcopy** avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="a4448-109">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="a4448-110">Lorsque tous les fichiers audio personnalisés ont été copiés dans le magasin de fichiers Lync Server 2013, les paramètres d’application de parcage d’appel du pool Lync Server 2013 doivent être configurés et les plages d’orbites de parcage d’appel associées au pool Lync Server 2010 doivent être réattribuées au pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4448-110">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="a4448-111">Les paramètres de l’application de parcage d’appel incluent le seuil du délai d’attente de prise d’appel, l’activation ou la désactivation de l’attente musicale, le nombre maximal de tentatives de prise d’appel et la demande de délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="a4448-111">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="a4448-112">Vous devez gérer les paramètres d’application de parcage d’appel à l’aide de Lync Server Management Shell pour exécuter la cmdlet **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a4448-112">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="a4448-113">Vous ne pouvez pas gérer les paramètres d’application de parcage d’appel à l’aide du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4448-113">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="a4448-114">**Reconfigurer les paramètres de l’application de parcage d’appel**</span><span class="sxs-lookup"><span data-stu-id="a4448-114">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="a4448-115">À partir du serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a4448-115">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="a4448-116">Dans la ligne de commande, tapez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="a4448-116">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a4448-117">Si vos paramètres d’application de parcage d’appel Lync Server 2013 sont identiques aux paramètres de Lync Server 2010 hérités, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="a4448-117">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="a4448-118">Si les paramètres d’application de parcage d’appel sont différents pour les environnements Lync Server 2013 et Lync Server 2010, utilisez l’applet de commande ci-dessous comme modèle pour mettre à jour ces modifications.</span><span class="sxs-lookup"><span data-stu-id="a4448-118">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="a4448-119"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-EnableMusicOnHold" <LS2010 CPS value> "-valeur maxcallpickupattempts" <LS2010 CPS pickup attempts> "-OnTimeoutURI" <LS2010 CPS timeout URI> " ```</span><span class="sxs-lookup"><span data-stu-id="a4448-119"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="a4448-120">Pour réaffecter toutes les plages d’orbites de parcage d’appel du pool Lync Server 2010 au pool Lync Server 2013, vous pouvez utiliser le panneau de configuration Lync Server ou Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a4448-120">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="a4448-121">**Réaffecter toutes les plages d’orbites de parcage d’appel à l’aide du Panneau de configuration Lync Server**</span><span class="sxs-lookup"><span data-stu-id="a4448-121">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="a4448-122">Ouvrez le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4448-122">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="a4448-123">Dans le volet gauche, sélectionnez **Fonctionnalités vocales**.</span><span class="sxs-lookup"><span data-stu-id="a4448-123">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="a4448-124">Sélectionnez l’onglet **Parcage d’appel**.</span><span class="sxs-lookup"><span data-stu-id="a4448-124">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="a4448-125">Pour chaque plage d’orbites de parcage d’appel attribuée à un pool Lync Server 2010, modifiez le paramètre **nom de domaine complet du serveur de destination** et sélectionnez le pool lync Server 2013 qui traitera les demandes de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="a4448-125">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="a4448-126">Sélectionnez **Valider** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="a4448-126">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="a4448-127">**Réaffecter toutes les plages d’orbites de parcage d’appel à l’aide de Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="a4448-127">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="a4448-128">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a4448-128">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="a4448-129">Sur la ligne de commande, tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a4448-129">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="a4448-130">Cette applet de commande répertorie toutes les plages d’orbites de parcage d’appel dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="a4448-130">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="a4448-131">Toutes les orbites de parcage d’appel dont les paramètres **CallParkServiceId** et **CallParkServerFqdn** sont définis en tant que pool Lync Server 2010 doivent être réaffectées.</span><span class="sxs-lookup"><span data-stu-id="a4448-131">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="a4448-132">Pour réaffecter les plages d’orbites de parcage d’appel Lync Server 2010 au pool Lync Server 2013, dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a4448-132">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="a4448-133">Après avoir réaffecté toutes les plages d’orbites de parcage d’appel au pool Lync Server 2013, le processus de migration de l’application de parcage d’appel est terminé et le pool Lync Server 2013 gère toutes les futures demandes de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="a4448-133">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

