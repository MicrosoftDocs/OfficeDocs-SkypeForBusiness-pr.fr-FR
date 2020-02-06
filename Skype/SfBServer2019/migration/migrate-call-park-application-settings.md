---
title: Migration des paramètres d’application de parcage d’appel
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La migration de l’application de parc d’appels inclut la mise en service du pool Skype entreprise Server 2019 avec n’importe quel fichier de musique personnalisé sur les fichiers qui ont été téléchargés dans l’installation héritée, en restaurant les paramètres de niveau de service et en reciblant toutes les orbites du parc d’appels sur le Pool 2019 de Skype entreprise Server. Si des fichiers personnalisés de musique en attente ont été configurés dans la liste, ces fichiers doivent être copiés dans le nouveau pool Skype entreprise Server 2019. Par ailleurs, il est recommandé de sauvegarder les fichiers de conservation de musique personnalisés de votre parc d’appels à partir d’une autre destination pour conserver une copie de sauvegarde distincte de tous les fichiers de conservation de la musique personnalisés qui ont été téléchargés pour le parc d’appels. Les fichiers de conservation de musique personnalisés pour l’application de parc d’appels sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio à partir d’un magasin de fichiers de réserve dans un magasin de fichiers 2019 Skype entreprise Server, utilisez la commande xcopy avec les paramètres suivants :'
ms.openlocfilehash: b9e55bc76e718d499482fb21e029a0a74e8f207f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813582"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="86f71-107">Migration des paramètres d’application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="86f71-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="86f71-108">La migration de l’application de parc d’appels inclut la mise en service du pool Skype entreprise Server 2019 avec des fichiers personnalisés de conservation de la musique qui ont été téléchargés dans l’installation héritée, en restaurant les paramètres de niveau de service et en reciblant tout le parc d’appels. au pool 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="86f71-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="86f71-109">Si des fichiers personnalisés de musique en attente ont été configurés dans la liste, ces fichiers doivent être copiés dans le nouveau pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="86f71-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="86f71-110">Par ailleurs, il est recommandé de sauvegarder les fichiers de mise en attente personnalisés de votre parc d’appels dans une autre destination pour conserver une copie de sauvegarde distincte de tous les fichiers de conservation de la musique personnalisés qui ont été téléchargés pour le parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="86f71-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="86f71-111">Les fichiers de conservation de musique personnalisés pour l’application de parc d’appels sont stockés dans le magasin de fichiers du pool.</span><span class="sxs-lookup"><span data-stu-id="86f71-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="86f71-112">Pour copier les fichiers audio à partir d’un magasin de fichiers de réserve dans un magasin de fichiers 2019 Skype entreprise Server, utilisez la commande **xcopy** avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="86f71-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="86f71-113">Lorsque tous les fichiers audio personnalisés ont été copiés dans le magasin de fichiers 2019 Skype entreprise Server, les paramètres d’application de parc d’appels du pool 2019 du serveur Skype entreprise doivent être configurés et les plages d’orbites du parc d’appels associées au pool hérité. doit être réaffecté au pool 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="86f71-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="86f71-114">Les paramètres de l’application de parc d’appels incluent le seuil de délai d’attente de capture, l’activation ou la désactivation de la musique en attente, le nombre maximal de tentatives de sélection d’appels et la demande d’expiration.</span><span class="sxs-lookup"><span data-stu-id="86f71-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="86f71-115">Vous devez gérer les paramètres de l’application parc d’appels à l’aide de Skype entreprise Server Management Shell pour exécuter l’applet de demande **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="86f71-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="86f71-116">Vous ne pouvez pas gérer les paramètres de l’application parc d’appels à l’aide du panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="86f71-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="86f71-117">Reconfigurer les paramètres du service de parc d’appels</span><span class="sxs-lookup"><span data-stu-id="86f71-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="86f71-118">À partir du serveur frontal Skype entreprise Server 2019, ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="86f71-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="86f71-119">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="86f71-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="86f71-120">Si vos paramètres d’application de parc d’appels Skype entreprise Server 2019 sont identiques à ceux de l’anciennement, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="86f71-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="86f71-121">Si les paramètres de l’application de parc d’appels diffèrent pour les environnements 2019 et hérités de Skype entreprise Server, utilisez l’applet de cmdlet ci-dessous en tant que modèle pour mettre à jour ces modifications.</span><span class="sxs-lookup"><span data-stu-id="86f71-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="86f71-122">Pour réattribuer toutes les plages d’orbites du parc d’appels à la liste de ressources partagées Skype entreprise Server 2019, vous pouvez utiliser le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="86f71-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="86f71-123">Réaffecter toutes les plages d’orbites du parc d’appels à l’aide de Skype entreprise Server panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="86f71-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="86f71-124">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="86f71-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="86f71-125">Dans le volet gauche, sélectionnez **fonctions vocales**.</span><span class="sxs-lookup"><span data-stu-id="86f71-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="86f71-126">Sélectionnez l’onglet **parc d’appels** .</span><span class="sxs-lookup"><span data-stu-id="86f71-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="86f71-127">Pour chaque gamme de parking d’appel attribuée à un pool hérité, modifiez le paramètre **de nom de domaine complet du serveur de destination** et sélectionnez le pool Skype entreprise Server 2019 qui traitera les demandes de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="86f71-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="86f71-128">Sélectionnez **valider** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="86f71-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="86f71-129">Réaffecter toutes les plages d’orbites du parc d’appels à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="86f71-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="86f71-130">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="86f71-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="86f71-131">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="86f71-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="86f71-132">Cette cmdlet recense toutes les plages d’orbites du parc d’appels du déploiement.</span><span class="sxs-lookup"><span data-stu-id="86f71-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="86f71-133">Toutes les orbites du parc d’appels avec les paramètres **CallParkServiceId** et **CallParkServerFqdn** définis comme le pool hérité doivent être réaffectées.</span><span class="sxs-lookup"><span data-stu-id="86f71-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="86f71-134">Pour réaffecter les plages d’orbites du parc d’appels à la liste de commande 2019 du serveur Skype entreprise, dans la ligne de commande, tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="86f71-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="86f71-135">Après avoir réaffecté toutes les plages d’orbite du parc téléphonique au pool 2019 de Skype entreprise Server, le processus de migration de l’application de parc d’appels sera exécuté et le pool de 2019 du serveur Skype entreprise gérera toutes les futures demandes de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="86f71-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


