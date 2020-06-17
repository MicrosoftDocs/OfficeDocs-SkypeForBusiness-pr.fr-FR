---
title: Migration des paramètres d’application de parcage d’appel
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La migration de l’application de parcage d’appel inclut la mise en service du pool Skype entreprise Server 2019 avec des fichiers de conservation musicaux personnalisés qui ont été téléchargés dans l’installation héritée, la restauration des paramètres de niveau de service et le reciblage de toutes les orbites de parcage d’appel vers le pool de Skype entreprise Server 2019. Si des fichiers de mise en attente musicale personnalisés ont été configurés dans le pool, ces fichiers doivent être copiés dans le nouveau pool Skype entreprise Server 2019. De plus, il est recommandé de sauvegarder tous les fichiers de conservation de musique personnalisée du parcage d’appel de vers une autre destination pour conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés qui ont été téléchargés pour le parcage d’appel. Les fichiers d’attente musicale personnalisée de l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio d’un magasin de fichiers de pool vers un magasin de fichiers 2019 de Skype entreprise, utilisez la commande xcopy avec les paramètres suivants :'
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752816"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="ee255-107">Migration des paramètres d’application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="ee255-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="ee255-108">La migration de l’application de parcage d’appel inclut la mise en service du pool Skype entreprise Server 2019 avec des fichiers de conservation de musique personnalisés qui ont été téléchargés dans l’installation héritée, la restauration des paramètres de niveau de service et le reciblage de toutes les orbites de parcage d’appel vers le pool de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ee255-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ee255-109">Si des fichiers de mise en attente musicale personnalisés ont été configurés dans le pool, ces fichiers doivent être copiés dans le nouveau pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ee255-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ee255-110">De plus, il est recommandé de sauvegarder tous les fichiers d’attente de musique personnalisés de parcage d’appel vers une autre destination pour conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés qui ont été téléchargés pour le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="ee255-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="ee255-111">Les fichiers d’attente musicale personnalisée de l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool.</span><span class="sxs-lookup"><span data-stu-id="ee255-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="ee255-112">Pour copier les fichiers audio d’un magasin de fichiers de pool vers un magasin de fichiers 2019 de Skype entreprise, utilisez la commande **xcopy** avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="ee255-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="ee255-113">Lorsque tous les fichiers audio personnalisés ont été copiés dans le magasin de fichiers de Skype entreprise Server 2019, les paramètres d’application de parcage d’appel du pool de Skype entreprise Server 2019 doivent être configurés et les plages d’orbites de parcage d’appel associées au pool hérité doivent être réattribuées au pool de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ee255-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="ee255-114">Les paramètres de l’application parcage d’appel incluent le seuil de délai d’expiration de la collecte, l’activation ou la désactivation de la conservation de la musique, le nombre maximal de tentatives de prise d’appel et la demande de délai d’attente.</span><span class="sxs-lookup"><span data-stu-id="ee255-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="ee255-115">Vous devez gérer les paramètres d’application de parcage d’appel à l’aide de Skype entreprise Server Management Shell pour exécuter la cmdlet **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="ee255-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="ee255-116">Vous ne pouvez pas gérer les paramètres de l’application parcage d’appel à l’aide du panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ee255-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="ee255-117">Reconfigurer les paramètres de l’application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="ee255-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="ee255-118">À partir du serveur frontal Skype entreprise Server 2019, ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ee255-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="ee255-119">Dans la ligne de commande, tapez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="ee255-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="ee255-120">Si vos paramètres d’application de parcage d’appel Skype entreprise Server 2019 sont identiques aux paramètres hérités, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="ee255-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="ee255-121">Si les paramètres d’application de parcage d’appel sont différents pour Skype entreprise Server 2019 et les environnements hérités, utilisez l’applet de commande ci-dessous comme modèle pour mettre à jour ces modifications.</span><span class="sxs-lookup"><span data-stu-id="ee255-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="ee255-122">Pour réaffecter toutes les plages d’orbites de parcage d’appel du pool hérité vers le pool Skype entreprise Server 2019, vous pouvez utiliser le panneau de configuration de Skype entreprise Server ou Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ee255-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ee255-123">Réaffecter toutes les plages d’orbites de parcage d’appel à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ee255-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ee255-124">Ouvrez le panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ee255-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ee255-125">Dans le volet gauche, sélectionnez **Fonctionnalités vocales**.</span><span class="sxs-lookup"><span data-stu-id="ee255-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="ee255-126">Sélectionnez l’onglet **Parcage d’appel**.</span><span class="sxs-lookup"><span data-stu-id="ee255-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="ee255-127">Pour chaque plage d’orbites de parcage d’appel affectée à un pool hérité, modifiez le paramètre **nom de domaine complet du serveur de destination** et sélectionnez le pool Skype entreprise Server 2019 qui traitera les demandes de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="ee255-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="ee255-128">Sélectionnez **Valider** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="ee255-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ee255-129">Réaffecter toutes les plages d’orbites de parcage d’appel à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ee255-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ee255-130">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ee255-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="ee255-131">Sur la ligne de commande, tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ee255-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="ee255-132">Cette applet de commande répertorie toutes les plages d’orbites de parcage d’appel dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="ee255-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="ee255-133">Toutes les orbites de parcage d’appel dont les paramètres **CallParkServiceId** et **CallParkServerFqdn** sont définis en tant que pool hérité doivent être réaffectées.</span><span class="sxs-lookup"><span data-stu-id="ee255-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="ee255-134">Pour réaffecter les plages d’orbites de parcage d’appel hérité au pool Skype entreprise Server 2019, dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ee255-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="ee255-135">Après avoir réaffecté toutes les plages d’orbites de parcage d’appel au pool Skype entreprise Server 2019, le processus de migration de l’application de parcage d’appel est terminé et le pool de Skype entreprise Server 2019 gère toutes les futures demandes de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="ee255-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


