---
title: Configuration et surveillance du service de sauvegarde
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez utiliser Skype pour les commandes Business Server Management Shell pour configurer et surveiller le Service de sauvegarde.
ms.openlocfilehash: 3a41caecb4e123505da2d529ea74c22a5d0e28e7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896832"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="b9b0b-103">Configuration et surveillance du Service de sauvegarde dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="b9b0b-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="b9b0b-104">Vous pouvez utiliser la Skype pour les commandes Business Server Management Shell suivante pour configurer et surveiller le Service de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="b9b0b-105">Pour restaurer les informations de conférence stockées dans le magasin de fichiers d’un pool frontal, voir [restaurer le contenu de conférence à l’aide du Service de sauvegarde](#restore-conference-contents-using-the-backup-service), ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="b9b0b-106">Groupe RTCUniversalServerAdmins est le seul groupe qui dispose d’autorisations pour exécuter **Get-csbackupservicestatus ne** par défaut.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="b9b0b-107">Pour utiliser cette applet de commande, ouvrez une session en tant que membre de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="b9b0b-108">Ou bien, vous pouvez accorder l’accès à cette commande à d’autres groupes (par exemple, CSAdministrator) à l’aide de l’applet de commande **Set-CsBackupServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b9b0b-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="b9b0b-109">Pour afficher la configuration du Service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b9b0b-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="b9b0b-110">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b9b0b-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="b9b0b-111">La valeur par défaut pour SyncInterval est de deux minutes.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="b9b0b-112">Pour définir l’intervalle de synchronisation du Service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b9b0b-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="b9b0b-113">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b9b0b-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="b9b0b-114">Par exemple, la commande suivante définit l’intervalle sur trois minutes.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="b9b0b-115">Bien que vous pouvez utiliser cette applet de commande pour modifier l’intervalle de synchronisation par défaut pour le Service de sauvegarde, vous ne, sauf si elle est absolument nécessaire, en tant que la synchronisation intervalle a un impact important sur les performances du Service de sauvegarde et de l’objectif de point de récupération (RPO).</span><span class="sxs-lookup"><span data-stu-id="b9b0b-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="b9b0b-116">Pour obtenir l’état du Service de sauvegarde pour un pool donné</span><span class="sxs-lookup"><span data-stu-id="b9b0b-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="b9b0b-117">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b9b0b-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="b9b0b-118">L’état de synchronisation du Service de sauvegarde est défini rubans à partir d’un pool (P1) à son pool de sauvegarde (P2).</span><span class="sxs-lookup"><span data-stu-id="b9b0b-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="b9b0b-119">L’état de synchronisation de P1 vers P2 peut être différent de celui de P2 à P1.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="b9b0b-120">Pour P1 vers P2, Service de sauvegarde est dans un état « stable » si toutes les modifications apportées dans P1 sont complètement répliquées sur P2 dans l’intervalle de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="b9b0b-121">Il n’est dans l’état « final » s’il y a aucune modification à être synchronisées à partir de P1 à P2.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="b9b0b-122">Les deux états indiquent un instantané du Service de sauvegarde au moment de que l’applet de commande est exécutée.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="b9b0b-123">Il n’implique pas que l’état renvoyé restera est par la suite.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="b9b0b-124">En particulier, l’état « final » continuera à contenir uniquement si P1 ne génère pas toutes les modifications après l’exécution de l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="b9b0b-125">Cela est vrai dans le cas de basculement P1 vers P2 après que P1 est placé dans le mode lecture seule dans le cadre de la logique d’exécution **Invoke-cspoolfailover ne** .</span><span class="sxs-lookup"><span data-stu-id="b9b0b-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="b9b0b-126">Pour obtenir des informations sur la relation de sauvegarde pour un pool donné</span><span class="sxs-lookup"><span data-stu-id="b9b0b-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="b9b0b-127">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b9b0b-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="b9b0b-128">Pour forcer une synchronisation du Service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b9b0b-128">To force a Backup Service sync</span></span>

<span data-ttu-id="b9b0b-129">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b9b0b-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="b9b0b-130">Restaurer le contenu de conférence à l’aide du Service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b9b0b-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="b9b0b-131">Si les informations de conférence stockées dans le magasin de fichiers d’un pool frontal devient indisponibles, vous devez restaurer ces informations afin que les utilisateurs hébergés sur le pool conservent leurs données de conférence.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="b9b0b-132">Si le pool frontal qui a perdu les données de conférence est associé à un autre pool frontal, vous pouvez utiliser le Service de sauvegarde à restaurer les données.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="b9b0b-133">Vous devez également effectuer cette tâche si un pool entier a échoué et vous avez à faire basculer les utilisateurs à un pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="b9b0b-134">Lorsque ces utilisateurs sont basculées retour vers leur pool d’origine, vous devez utiliser cette procédure pour copier leur contenu de conférence à leur pool de d’origine.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="b9b0b-135">Supposons que Pool1 est associé à Pool2, et les données de conférence dans Pool1 sont perdues.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="b9b0b-136">Vous pouvez utiliser la cmdlet suivante pour appeler le Service de sauvegarde pour restaurer le contenu :</span><span class="sxs-lookup"><span data-stu-id="b9b0b-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="b9b0b-137">Restaurer le contenu de conférence peut prendre un certain temps, en fonction de leur taille.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="b9b0b-138">Vous pouvez utiliser l’applet de commande suivante pour vérifier l’état du processus :</span><span class="sxs-lookup"><span data-stu-id="b9b0b-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="b9b0b-139">Le processus est terminé une fois cette applet de commande renvoie une valeur d’état stable pour le module de conférence de données.</span><span class="sxs-lookup"><span data-stu-id="b9b0b-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
