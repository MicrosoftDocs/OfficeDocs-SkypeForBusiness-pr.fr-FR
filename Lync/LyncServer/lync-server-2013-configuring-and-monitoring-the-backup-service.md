---
title: 'Lync Server 2013 : configuration et surveillance du service de sauvegarde'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65fbbf4db9e15eac2d29fcde6bd126355c794a95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="e5eaf-102">Configuration et surveillance du service de sauvegarde dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5eaf-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5eaf-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e5eaf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e5eaf-104">Vous pouvez utiliser les commandes Lync Server Management Shell suivantes pour configurer et surveiller le service de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="e5eaf-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5eaf-105">Le groupe RTCUniversalServerAdmins est le seul groupe disposant des autorisations pour exécuter <STRONG>Get-CsBackupServiceStatus</STRONG> par défaut.</span><span class="sxs-lookup"><span data-stu-id="e5eaf-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="e5eaf-106">Pour utiliser cette applet de commande, ouvrez une session en tant que membre de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="e5eaf-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="e5eaf-107">Ou, vous pouvez accorder l’accès à cette commande à d’autres groupes (par exemple, CSAdministrator) à l’aide de la cmdlet <STRONG>Set-applet csbackupserviceconfiguration ne</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e5eaf-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="e5eaf-108">Pour afficher la configuration du service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="e5eaf-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="e5eaf-109">Exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="e5eaf-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="e5eaf-110">La valeur par défaut pour SyncInterval est de deux minutes.</span><span class="sxs-lookup"><span data-stu-id="e5eaf-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="e5eaf-111">Pour définir l’intervalle de synchronisation du service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="e5eaf-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="e5eaf-112">Exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="e5eaf-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="e5eaf-113">Par exemple, le code suivant définit l’intervalle à trois minutes.</span><span class="sxs-lookup"><span data-stu-id="e5eaf-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e5eaf-114">Bien que vous puissiez utiliser cette applet de commande pour modifier l’intervalle de synchronisation par défaut pour le service de sauvegarde, vous ne devez pas le faire sauf si cela est absolument nécessaire, car l’intervalle de synchronisation a un fort impact sur les performances du service de sauvegarde et l’objectif de point de récupération (RPO).</span><span class="sxs-lookup"><span data-stu-id="e5eaf-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="e5eaf-115">Pour obtenir l’état du service de sauvegarde pour un pool particulier</span><span class="sxs-lookup"><span data-stu-id="e5eaf-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="e5eaf-116">Exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="e5eaf-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="e5eaf-117">L’état de synchronisation du service de sauvegarde est défini de façon unidirectionnelle à partir d’un pool (P1) vers son pool de sauvegarde (P2).</span><span class="sxs-lookup"><span data-stu-id="e5eaf-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="e5eaf-118">L’état de synchronisation de P1 à P2 peut être différent de celui de P2 à P1.</span><span class="sxs-lookup"><span data-stu-id="e5eaf-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="e5eaf-119">Pour P1 à P2, le service de sauvegarde est dans un état « stable » si toutes les modifications apportées à P1 sont entièrement répliquées sur P2 dans l’intervalle de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="e5eaf-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="e5eaf-120">Il se trouve dans l’état « final » s’il n’y a plus de modifications à synchroniser de P1 à P2.</span><span class="sxs-lookup"><span data-stu-id="e5eaf-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="e5eaf-121">Les deux États indiquent un instantané du service de sauvegarde au moment de l’exécution de la cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5eaf-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="e5eaf-122">Cela ne signifie pas que l’état renvoyé restera le même.</span><span class="sxs-lookup"><span data-stu-id="e5eaf-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="e5eaf-123">En particulier, l’état « final » reste en conservation uniquement si P1 ne génère pas de modifications après l’exécution de la cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5eaf-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="e5eaf-124">Cela est vrai en cas de défaillance de P1 sur P2 après que P1 est placé dans le mode lecture seule dans le cadre de la logique d’exécution <STRONG>Invoke-applet cspoolfailover ne</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e5eaf-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="e5eaf-125">Pour obtenir des informations sur la relation de sauvegarde pour un pool particulier</span><span class="sxs-lookup"><span data-stu-id="e5eaf-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="e5eaf-126">Exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="e5eaf-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="e5eaf-127">Pour forcer une synchronisation du service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="e5eaf-127">To force a Backup Service sync</span></span>

<span data-ttu-id="e5eaf-128">Exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="e5eaf-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

