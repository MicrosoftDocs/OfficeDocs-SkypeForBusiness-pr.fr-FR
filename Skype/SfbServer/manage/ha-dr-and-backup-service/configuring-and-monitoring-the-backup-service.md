---
title: Configuration et surveillance du service de sauvegarde
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez utiliser les commandes de Skype entreprise Server Management Shell pour configurer et surveiller le service de sauvegarde.
ms.openlocfilehash: 2170f58fcc60a648788934048f3d0e6bbfac9c77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303904"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="a1a36-103">Configuration et analyse du service de sauvegarde dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a1a36-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="a1a36-104">Vous pouvez utiliser les commandes Skype entreprise Server Management Shell suivantes pour configurer et surveiller le service de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a1a36-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="a1a36-105">Pour restaurer des informations de conférence stockées dans le magasin de fichiers d’un pool frontal, voir [restaurer le contenu de la Conférence à l’aide du service de sauvegarde](#restore-conference-contents-using-the-backup-service), ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a1a36-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="a1a36-106">Le groupe RTCUniversalServerAdmins est le seul groupe qui dispose des autorisations d’exécution par défaut de **Get-CsBackupServiceStatus** .</span><span class="sxs-lookup"><span data-stu-id="a1a36-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="a1a36-107">Pour utiliser cette applet de connexion, connectez-vous en tant que membre du groupe.</span><span class="sxs-lookup"><span data-stu-id="a1a36-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="a1a36-108">Ou, vous pouvez accorder l’accès à cette commande à d’autres groupes (par exemple, CSAdministrator) à l’aide de l’applet de commande **Set-CsBackupServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a1a36-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="a1a36-109">Pour afficher la configuration du service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a1a36-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="a1a36-110">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a1a36-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="a1a36-111">La valeur par défaut de SyncInterval est de deux minutes.</span><span class="sxs-lookup"><span data-stu-id="a1a36-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="a1a36-112">Pour définir l’intervalle de synchronisation du service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a1a36-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="a1a36-113">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a1a36-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="a1a36-114">Par exemple, la valeur suivante définit l’intervalle à 3 minutes.</span><span class="sxs-lookup"><span data-stu-id="a1a36-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="a1a36-115">Même si vous pouvez utiliser cette applet de action pour modifier l’intervalle de synchronisation par défaut du service de sauvegarde, vous ne devez pas le faire sauf si cela est absolument nécessaire, car l’intervalle de synchronisation a un impact important sur les performances du service de sauvegarde et de l’objectif de point de récupération (RPO).</span><span class="sxs-lookup"><span data-stu-id="a1a36-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="a1a36-116">Pour obtenir l’état du service de sauvegarde pour un pool particulier</span><span class="sxs-lookup"><span data-stu-id="a1a36-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="a1a36-117">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a1a36-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="a1a36-118">L’état de synchronisation du service de sauvegarde est défini de façon unidirectionnelle à partir d’un pool (P1) vers son pool de sauvegarde (P2).</span><span class="sxs-lookup"><span data-stu-id="a1a36-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="a1a36-119">L’état de synchronisation de P1 à P2 peut être différent de celui de P2 à P1.</span><span class="sxs-lookup"><span data-stu-id="a1a36-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="a1a36-120">Pour P1 à P2, le service de sauvegarde est dans un état «permanent» si toutes les modifications apportées à P1 sont entièrement répliquées dans le cadre de l’intervalle de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="a1a36-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="a1a36-121">Il est dans l’état «final» s’il n’y a plus de modifications à synchroniser entre P1 et P2.</span><span class="sxs-lookup"><span data-stu-id="a1a36-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="a1a36-122">Les deux États indiquent une capture instantanée du service de sauvegarde au moment de l’exécution de l’applet de connexion.</span><span class="sxs-lookup"><span data-stu-id="a1a36-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="a1a36-123">Cela ne signifie pas que l’état renvoyé sera le plus tard possible.</span><span class="sxs-lookup"><span data-stu-id="a1a36-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="a1a36-124">En particulier, l’état «final» reste en attente uniquement si P1 ne génère aucune modification après l’exécution de l’applet de suspension.</span><span class="sxs-lookup"><span data-stu-id="a1a36-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="a1a36-125">C’est vrai en cas d’échec de P1 sur P2 après que P1 est passé dans le mode lecture seule dans le cadre de la logique d’exécution d' **Invoke-CsPoolfailover** .</span><span class="sxs-lookup"><span data-stu-id="a1a36-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="a1a36-126">Pour obtenir des informations sur la relation de sauvegarde d’un pool particulier</span><span class="sxs-lookup"><span data-stu-id="a1a36-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="a1a36-127">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a1a36-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="a1a36-128">Pour forcer la synchronisation du service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a1a36-128">To force a Backup Service sync</span></span>

<span data-ttu-id="a1a36-129">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a1a36-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="a1a36-130">Restaurer le contenu d’une conférence à l’aide du service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a1a36-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="a1a36-131">Si les informations de la Conférence stockées dans le magasin de fichiers d’un pool frontal deviennent indisponibles, vous devez restaurer ces informations de sorte que les utilisateurs hébergés sur le pool conservent leurs données de conférence.</span><span class="sxs-lookup"><span data-stu-id="a1a36-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="a1a36-132">Si le pool frontal qui a perdu les données de conférence est associé à un autre pool frontal, vous pouvez utiliser le service de sauvegarde pour restaurer les données.</span><span class="sxs-lookup"><span data-stu-id="a1a36-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="a1a36-133">Vous devez également effectuer cette tâche si un pool entier a échoué et que vous devez faire basculer ses utilisateurs vers un pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a1a36-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="a1a36-134">Lorsque les utilisateurs ont basculé vers leur pool d’origine, vous devez utiliser cette procédure pour copier le contenu de la Conférence sur leur pool d’origine.</span><span class="sxs-lookup"><span data-stu-id="a1a36-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="a1a36-135">Supposez que Pool1 est associé à Pool2, et les données de conférence en Pool1 sont perdues.</span><span class="sxs-lookup"><span data-stu-id="a1a36-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="a1a36-136">Vous pouvez utiliser l’applet de commande suivante pour appeler le service de sauvegarde et restaurer le contenu:</span><span class="sxs-lookup"><span data-stu-id="a1a36-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="a1a36-137">La restauration du contenu de la Conférence risque de prendre un certain temps en fonction de la taille de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="a1a36-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="a1a36-138">Pour vérifier l’état du processus, vous pouvez utiliser l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="a1a36-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="a1a36-139">Le processus est réalisé lorsque cette cmdlet renvoie une valeur d’état stable pour le module de conférence de données.</span><span class="sxs-lookup"><span data-stu-id="a1a36-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
