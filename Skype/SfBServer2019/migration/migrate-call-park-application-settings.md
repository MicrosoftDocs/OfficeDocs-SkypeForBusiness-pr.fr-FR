---
title: Migrer les paramètres d’application de parcage d’appel
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La migration de l’application inclut la Skype pour le pool d’entreprise Server 2019 avec n’importe quel musique personnalisée sur les fichiers d’attente qui ont été téléchargés dans l’installation héritée de mise en service le parcage d’appel, la restauration des paramètres de niveau de service et reciblage parcage d’appel toutes les orbites à la Skype pour Business Server 2019 pool. Si les fichiers de musique attente personnalisés ont été configurés dans le pool, ces fichiers doivent être copiés à la nouvelle Skype pour Business Server 2019 pool. En outre, il est recommandé que vous sauvegardez toute mise en garde d’appels personnalisé musique d’attente dans une fichiers à partir d’une autre destination pour conserver une copie de sauvegarde distincte des fichiers musique attente personnalisés qui ont été téléchargés parcage d’appel. Les fichiers de musique attente personnalisés pour l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio à partir d’un magasin de fichiers du pool vers un Skype Business Server 2019 magasin de fichiers, utilisez la commande Copier (XCOPY) avec les paramètres suivants :'
ms.openlocfilehash: a91c23f06d22d822567bd39ec9f18eb7289e201d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028823"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="d8dfd-107">Migrer les paramètres d’application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="d8dfd-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="d8dfd-108">La migration de l’application de parcage d’appel inclut la mise en service le Skype pour Business Server 2019 pool avec les fichiers de musique attente personnalisés qui ont été téléchargés dans l’installation héritée, la restauration des paramètres de niveau de service et re-ciblage toutes les orbites de parcage d’appel pour Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="d8dfd-109">Si les fichiers de musique attente personnalisés ont été configurés dans le pool, ces fichiers doivent être copiés à la nouvelle Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="d8dfd-110">En outre, il est recommandé que vous sauvegardez toute mise en garde d’appels personnalisé des fichiers de musique en attente vers une autre destination pour conserver une copie de sauvegarde distincte des fichiers musique attente personnalisés qui ont été téléchargés parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="d8dfd-111">Les fichiers de musique attente personnalisés pour l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="d8dfd-112">Pour copier les fichiers audio à partir d’un magasin de fichiers du pool vers un Skype Business Server 2019 magasin de fichiers, utilisez la commande **Copier (XCOPY)** avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="d8dfd-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 
  
```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="d8dfd-113">Lorsque tous les fichiers audio personnalisés ont été copiés vers la Skype Business Server 2019 magasin de fichiers, les paramètres d’application de parcage d’appel de la Skype pour Business Server 2019 pool doit être configuré et la mise en garde d’appels orbite plages associés avec le pool hérité doit être réaffecté à la Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>
  
<span data-ttu-id="d8dfd-114">Les paramètres d’application de parcage d’appel incluent le seuil de délai d’expiration pickup, activation ou désactivation d’une musique d’attente, les tentatives de collecte de nombre maximal d’appels et la demande de délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="d8dfd-115">Vous devez gérer les paramètres de l’application parcage d’appel à l’aide de la Skype pour Business Server Management Shell pour exécuter l’applet de commande **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d8dfd-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="d8dfd-116">Vous ne pouvez pas gérer les paramètres d’application de parcage d’appel à l’aide de la Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 
  
## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="d8dfd-117">Reconfigurer les paramètres de Service de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="d8dfd-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="d8dfd-118">Skype pour Business Server 2019 serveur frontal, ouvrez le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="d8dfd-119">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d8dfd-119">At the command line, type the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d8dfd-120">Si votre Skype pour les paramètres de l’application Business Server 2019 Call Park est identique aux paramètres hérités, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="d8dfd-121">Si les paramètres de l’application parcage d’appel sont différentes pour le Skype pour Business Server 2019 et environnements hérités, utilisez l’applet de commande ci-dessous en tant que modèle pour mettre à jour ces modifications.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 
  
  ```
  Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
  
  ```

<span data-ttu-id="d8dfd-122">Pour réaffecter toutes les plages d’orbites parcage d’appel du pool hérité vers le Skype pour Business Server 2019 pool, vous pouvez utiliser la Skype pour le panneau de configuration serveur Business soit le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 
  
## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d8dfd-123">Réaffecter toutes les plages d’orbites parcage d’appel à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="d8dfd-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d8dfd-124">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-124">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="d8dfd-125">Dans le volet gauche, sélectionnez **Fonctionnalités vocales**.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-125">In the left pane, select **Voice Features**.</span></span>
    
3. <span data-ttu-id="d8dfd-126">Sélectionnez l’onglet **Mise en garde d’appels** .</span><span class="sxs-lookup"><span data-stu-id="d8dfd-126">Select the **Call Park** tab.</span></span> 
    
4. <span data-ttu-id="d8dfd-127">Pour chaque plage d’orbites de parcage d’appel affecté à un pool hérité, modifiez le paramètre de **nom de domaine complet du serveur de destination** et sélectionnez le Skype pour le pool d’entreprise Server 2019 qui traitera les demandes de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 
    
5. <span data-ttu-id="d8dfd-128">Sélectionnez **Valider** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-128">Select **Commit** to save the changes.</span></span> 
    
## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d8dfd-129">Réaffecter toutes les plages d’orbites parcage d’appel à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d8dfd-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d8dfd-130">Ouvrez Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-130">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="d8dfd-131">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d8dfd-131">At the command line, type the following:</span></span>
    
  ```
  Get-CsCallParkOrbit
  ```

    <span data-ttu-id="d8dfd-132">Cette applet de commande répertorie toutes les plages d’orbites de parcage d’appel dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="d8dfd-133">Toutes les orbites de parcage d’appel dont les paramètres **CallParkServiceId** et **CallParkServerFqdn** en tant que le pool hérité doivent être réaffectés.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 
    
    <span data-ttu-id="d8dfd-134">Pour réaffecter l’orbite de parcage d’appel hérité des plages à le Skype pour le pool d’entreprise Server 2019, sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d8dfd-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>
    
  ```
  Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
  
  ```

<span data-ttu-id="d8dfd-135">Après avoir réaffecté toutes les plages d’orbites de parcage d’appel à la Skype pour Business Server 2019 pool, le processus de migration pour l’application de parcage d’appel se termine et le Skype pour le pool d’entreprise Server 2019 gère toutes les futures demandes de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="d8dfd-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>
  

