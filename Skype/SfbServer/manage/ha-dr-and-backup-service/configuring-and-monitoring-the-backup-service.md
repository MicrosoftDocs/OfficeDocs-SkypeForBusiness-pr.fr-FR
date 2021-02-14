---
title: Configuration et surveillance du service de sauvegarde
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vous pouvez utiliser les commandes Skype Entreprise Server Management Shell pour configurer et surveiller le service de sauvegarde.
ms.openlocfilehash: d38c9d0b0261fb7e1da89b3422496d94307a791d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817194"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="bf0d5-103">Configuration et surveillance du service de sauvegarde dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bf0d5-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="bf0d5-104">Vous pouvez utiliser les commandes Skype Entreprise Server Management Shell suivantes pour configurer et surveiller le service de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="bf0d5-105">Pour restaurer les informations de conférence stockées dans le magasin de fichiers d’un pool frontal, voir Restaurer le contenu de la conférence à l’aide du [service](#restore-conference-contents-using-the-backup-service)de sauvegarde, ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="bf0d5-106">Le groupe RTCUniversalServerAdmins est le seul groupe autorisé à exécuter **Get-CsBackupServiceStatus** par défaut.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="bf0d5-107">Pour utiliser cette cmdlet, connectez-vous en tant que membre de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="bf0d5-108">Vous pouvez également accorder l’accès à cette commande à d’autres groupes  (par exemple, CSAdministrator) à l’aide de l';</span><span class="sxs-lookup"><span data-stu-id="bf0d5-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="bf0d5-109">Pour voir la configuration du service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="bf0d5-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="bf0d5-110">Exécutez la l’applet commande suivant :</span><span class="sxs-lookup"><span data-stu-id="bf0d5-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="bf0d5-111">La valeur par défaut de SyncInterval est de deux minutes.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="bf0d5-112">Pour définir l’intervalle de synchronisation du service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="bf0d5-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="bf0d5-113">Exécutez la l’applet commande suivant :</span><span class="sxs-lookup"><span data-stu-id="bf0d5-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="bf0d5-114">Par exemple, l’exemple suivant définit l’intervalle sur trois minutes.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="bf0d5-115">Bien que vous pouvez utiliser cette cmdlet pour modifier l’intervalle de synchronisation par défaut pour le service de sauvegarde, vous ne devez pas le faire sauf si cela est absolument nécessaire, car l’intervalle de synchronisation a un impact significatif sur les performances du service de sauvegarde et l’objectif de point de récupération (RPO).</span><span class="sxs-lookup"><span data-stu-id="bf0d5-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="bf0d5-116">Pour obtenir l’état du service de sauvegarde pour un pool particulier</span><span class="sxs-lookup"><span data-stu-id="bf0d5-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="bf0d5-117">Exécutez la l’applet commande suivant :</span><span class="sxs-lookup"><span data-stu-id="bf0d5-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="bf0d5-118">L’état de synchronisation du service de sauvegarde est défini de manière unidirectionnelle d’un pool (P1) vers son pool de sauvegarde (P2).</span><span class="sxs-lookup"><span data-stu-id="bf0d5-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="bf0d5-119">L’état de synchronisation de P1 à P2 peut être différent de celui de P2 à P1.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="bf0d5-120">Pour P1 à P2, le service de sauvegarde est dans un état « stable » si toutes les modifications apportées dans P1 sont entièrement répliquées sur P2 au cours de l’intervalle de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="bf0d5-121">Il est dans l’état « final » s’il n’y a plus de modifications à synchroniser de P1 à P2.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="bf0d5-122">Les deux états indiquent un instantané du service de sauvegarde au moment de l’exécution de la cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="bf0d5-123">Cela ne signifie pas que l’état renvoyé restera tel quel par la suite.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="bf0d5-124">En particulier, l’état « final » continuera de se maintenir uniquement si P1 ne génère aucune modification après l’exécution de l’cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="bf0d5-125">Cela est vrai dans le cas d’un passage de P1 à P2 après que P1 est placé en mode lecture seule dans le cadre de la logique d’exécution **Invoke-CsPoolfailover.**</span><span class="sxs-lookup"><span data-stu-id="bf0d5-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="bf0d5-126">Pour obtenir des informations sur la relation de sauvegarde pour un pool particulier</span><span class="sxs-lookup"><span data-stu-id="bf0d5-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="bf0d5-127">Exécutez la l’applet commande suivant :</span><span class="sxs-lookup"><span data-stu-id="bf0d5-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="bf0d5-128">Pour forcer la synchronisation d’un service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="bf0d5-128">To force a Backup Service sync</span></span>

<span data-ttu-id="bf0d5-129">Exécutez la l’applet commande suivant :</span><span class="sxs-lookup"><span data-stu-id="bf0d5-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="bf0d5-130">Restaurer le contenu des conférences à l’aide du service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="bf0d5-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="bf0d5-131">Si les informations de conférence stockées dans le magasin de fichiers d’un pool frontal deviennent indisponibles, vous devez restaurer ces informations afin que les utilisateurs qui y sont stockés conservent leurs données de conférence.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="bf0d5-132">Si le pool frontal qui a perdu des données de conférence est associé à un autre pool frontal, vous pouvez utiliser le service de sauvegarde pour restaurer les données.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="bf0d5-p105">Vous devez aussi effectuer cette tâche en cas de panne d’un pool entier et basculer ses utilisateurs sur un pool de sauvegarde. Quand ces utilisateurs sont rebasculés sur leur pool d’origine, vous devez également exécuter cette procédure pour recopier leur contenu de référence sur le pool d’origine.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-p105">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="bf0d5-135">Supposons que Pool1 est couplé à Pool2 et que les données de conférence de Pool1 sont perdues.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="bf0d5-136">Vous pouvez utiliser l’cmdlet suivante pour appeler le service de sauvegarde afin de restaurer le contenu :</span><span class="sxs-lookup"><span data-stu-id="bf0d5-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="bf0d5-p107">La restauration du contenu de conférence peut prendre un certain temps, qui est fonction de sa taille. Vous pouvez utiliser l’applet de commande suivante pour vérifier l’état du processus</span><span class="sxs-lookup"><span data-stu-id="bf0d5-p107">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="bf0d5-139">Le processus est terminé une fois que cette applet de commande a retourné une valeur d’état stable pour les données du module de conférence.</span><span class="sxs-lookup"><span data-stu-id="bf0d5-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
