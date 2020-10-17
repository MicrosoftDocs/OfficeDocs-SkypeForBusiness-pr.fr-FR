---
title: 'Lync Server 2013 : gestion des annonces lors de la récupération d’urgence'
description: 'Lync Server 2013 : gestion des annonces lors de la récupération d’urgence.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d85dfcd15c9c3650bafafa6fa7702e19ac9c4f7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550630"
---
# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="f264f-103">Gérer les annonces lors de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f264f-103">Manage announcements during disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f264f-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f264f-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f264f-105">Lync Server 2013 prend en charge les annonces pour les appels à des numéros non attribués pendant les pannes.</span><span class="sxs-lookup"><span data-stu-id="f264f-105">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="f264f-106">La restauration de la fonctionnalité d’annonces en cas de panne est facultative.</span><span class="sxs-lookup"><span data-stu-id="f264f-106">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="f264f-107">Si vous choisissez cette option, vous devez recréer la configuration de vos annonces dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f264f-107">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="f264f-108">Cette section décrit les étapes à effectuer pour pouvoir restaurer les annonces dans le cadre d’une récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f264f-108">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="f264f-109">Cette section s’applique aux plages de numéros non attribués qui utilisent l’application annonce.</span><span class="sxs-lookup"><span data-stu-id="f264f-109">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="f264f-110">Elle ne s’applique pas aux plages de numéros non attribués du standard automatique de la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="f264f-110">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="f264f-111">Avant une panne</span><span class="sxs-lookup"><span data-stu-id="f264f-111">Before an Outage</span></span>

<span data-ttu-id="f264f-112">Que vous choisissiez ou non d’utiliser des annonces en cas de panne, vous devez effectuer des sauvegardes distinctes des fichiers audio personnalisés que vous avez configurés pour l’application d’annonce.</span><span class="sxs-lookup"><span data-stu-id="f264f-112">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="f264f-113">Les annonces personnalisées ne sont pas sauvegardées dans le cadre du processus de récupération d’urgence de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f264f-113">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="f264f-114">Si vous n’effectuez pas de sauvegardes distinctes des fichiers et que les fichiers que vous avez téléchargés sur le serveur ou le pool sont endommagés, endommagés ou effacés, les fichiers seront perdus.</span><span class="sxs-lookup"><span data-stu-id="f264f-114">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="f264f-115">Si vous n’avez pas de copie de sauvegarde des fichiers audio personnalisés et que les fichiers audio d’origine ne sont plus disponibles, vous pouvez trouver les fichiers audio que vous avez configurés pour une application d’annonce en recherchant dans le magasin de fichiers du serveur ou du pool où vous avez importé les fichiers à l’origine.</span><span class="sxs-lookup"><span data-stu-id="f264f-115">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="f264f-116">Vous pouvez copier tous les fichiers audio que vous avez configurés pour l’application d’annonce à partir du magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f264f-116">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="f264f-117">**Pour copier des fichiers audio à partir du magasin de fichiers**</span><span class="sxs-lookup"><span data-stu-id="f264f-117">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="f264f-118">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f264f-118">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="f264f-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f264f-119">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="f264f-120">Où X-ApplicationServer-X désigne l’ID de service du serveur d’applications du pool (par exemple, « 1-ApplicationServer-1 »).</span><span class="sxs-lookup"><span data-stu-id="f264f-120">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="f264f-121">Lors d’une panne</span><span class="sxs-lookup"><span data-stu-id="f264f-121">During an Outage</span></span>

<span data-ttu-id="f264f-122">Pour utiliser l’application d’annonce pendant une panne, vous devez recréer la configuration des annonces dans le pool de sauvegarde en exécutant les tâches décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="f264f-122">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f264f-123">Nous vous recommandons d’effectuer ces étapes après le basculement vers le pool de sauvegarde. En effet, dès que vous avez terminé l’étape 2, le pool de sauvegarde devient propriétaire des plages de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="f264f-123">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f264f-124">Ces étapes ne sont pas requises pour les plages de numéros qui utilisent un numéro de téléphone du standard automatique de la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="f264f-124">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="f264f-125">**Pour recréer la configuration des annonces dans le pool de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="f264f-125">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="f264f-126">Recréez dans le pool de sauvegarde les annonces initialement déployées dans le pool principal en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="f264f-126">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="f264f-127">Importez les fichiers audio du pool principal dans le pool de sauvegarde en exécutant l’applet de commande **Import-CsAnnouncementFile** et en spécifiant le pool de sauvegarde dans le paramètre Parent.</span><span class="sxs-lookup"><span data-stu-id="f264f-127">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="f264f-128">Recréez chaque annonce en exécutant l’applet de commande **New-CsAnnouncement** et en spécifiant le pool de sauvegarde dans le paramètre Parent.</span><span class="sxs-lookup"><span data-stu-id="f264f-128">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f264f-129">Pour plus d’informations sur l’utilisation de ces paramètres pour créer des annonces dans le pool de sauvegarde, voir <A href="lync-server-2013-create-an-announcement.md">Create an Announcement in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f264f-129">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="f264f-130">Lorsque vous avez fini de recréer toutes les annonces dans le pool de sauvegarde, redirigez toutes les plages de numéros non attribués associées aux annonces du pool principal vers les nouvelles annonces du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f264f-130">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="f264f-131">Pour chaque plage de numéros non attribués associée à une annonce du pool principal, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f264f-131">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="f264f-132">Après la panne</span><span class="sxs-lookup"><span data-stu-id="f264f-132">After the Outage</span></span>

<span data-ttu-id="f264f-133">Lorsque le pool principal est redevenu disponible, vous devez rediriger vers ce pool toutes les plages de numéros non attribués que vous avez modifiées lors de la panne.</span><span class="sxs-lookup"><span data-stu-id="f264f-133">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f264f-134">Ces étapes ne sont pas requises pour les plages de numéros qui utilisent un numéro de téléphone du standard automatique de la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="f264f-134">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="f264f-135">**Pour restaurer des annonces dans le pool principal**</span><span class="sxs-lookup"><span data-stu-id="f264f-135">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="f264f-p105">Si vous avez dû recréer le pool principal lors de la récupération d’urgence, vous devez maintenant restaurer les annonces dans ce pool en important les fichiers audio et en recréant les annonces. La procédure est la même que celle utilisée pour recréer les annonces dans le pool de sauvegarde, sauf que vous devez spécifier le pool principal dans le paramètre Parent au lieu du pool de sauvegarde. Pour plus d’informations, voir la section « Lors d’une panne », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="f264f-p105">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter. For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="f264f-138">Pour chaque plage de numéros non attribués ayant été modifiée lors de la panne, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f264f-138">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="f264f-139">Si vous le souhaitez, supprimez les annonces que vous avez recréées dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f264f-139">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="f264f-140">Obtenir la liste des annonces pour l’application d’annonce de pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f264f-140">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="f264f-141">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f264f-141">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="f264f-142">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f264f-142">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="f264f-p107">Dans la liste affichée, recherchez les annonces que vous voulez supprimer et copiez leur GUID respectif. Pour chaque annonce à supprimer, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f264f-p107">In the resulting list, locate the announcements you want to remove and copy the GUIDs. For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="f264f-145">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f264f-145">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

