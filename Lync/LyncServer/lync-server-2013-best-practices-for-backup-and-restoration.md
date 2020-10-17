---
title: 'Lync Server 2013 : meilleures pratiques pour la sauvegarde et la restauration'
description: 'Lync Server 2013 : meilleures pratiques pour la sauvegarde et la restauration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e8875f03a7b4445af8274ef059f3abad4d21ff8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552170"
---
# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="1ea37-103">Meilleures pratiques pour la sauvegarde et la restauration pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ea37-103">Best practices for backup and restoration for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ea37-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1ea37-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1ea37-105">Cette section comprend deux types de meilleures pratiques :</span><span class="sxs-lookup"><span data-stu-id="1ea37-105">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="1ea37-106">Meilleures pratiques pour la sauvegarde et la restauration.</span><span class="sxs-lookup"><span data-stu-id="1ea37-106">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="1ea37-107">Meilleures pratiques pour limiter l’impact d’un sinistre.</span><span class="sxs-lookup"><span data-stu-id="1ea37-107">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="1ea37-108">Meilleures pratiques de sauvegarde et restauration</span><span class="sxs-lookup"><span data-stu-id="1ea37-108">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="1ea37-109">Pour faciliter le processus de sauvegarde et de restauration, appliquez les meilleures pratiques suivantes lors de la sauvegarde ou de la restauration de vos données :</span><span class="sxs-lookup"><span data-stu-id="1ea37-109">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="1ea37-110">Effectuez des sauvegardes régulières, à intervalles adéquats.</span><span class="sxs-lookup"><span data-stu-id="1ea37-110">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="1ea37-111">Le type de sauvegarde et le planning de rotation les plus simples et les plus couramment utilisés consistent à effectuer chaque nuit une sauvegarde complète de la base de données SQL Server entière.</span><span class="sxs-lookup"><span data-stu-id="1ea37-111">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="1ea37-112">Ensuite, si la restauration est nécessaire, le processus de restauration ne nécessite qu’une seule sauvegarde et aucune donnée de jour ne doit être perdue.</span><span class="sxs-lookup"><span data-stu-id="1ea37-112">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="1ea37-113">Si vous utilisez des applets de commande ou le panneau de configuration Lync Server pour effectuer des modifications de configuration, utilisez la cmdlet **Export-CsConfiguration** pour effectuer une sauvegarde instantanée du fichier de configuration de topologie (XDS. mdf) après avoir apporté les modifications, afin de ne pas perdre les modifications si vous devez restaurer vos bases de données.</span><span class="sxs-lookup"><span data-stu-id="1ea37-113">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="1ea37-114">Notez que cette configuration est sauvegardée au format XML et compressée sous la forme d’un fichier. ZIP.</span><span class="sxs-lookup"><span data-stu-id="1ea37-114">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="1ea37-115">Assurez-vous que le dossier partagé que vous envisagez d’utiliser pour la sauvegarde de Lync Server dispose de suffisamment d’espace disque pour contenir toutes les données sauvegardées.</span><span class="sxs-lookup"><span data-stu-id="1ea37-115">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="1ea37-116">Planifiez les sauvegardes lorsque l’utilisation de Lync Server est généralement faible, pour améliorer les performances du serveur et l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1ea37-116">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="1ea37-117">Assurez-vous que l’emplacement où vous sauvegardez les données est sécurisé (nous vous recommandons d’utiliser un emplacement distant).</span><span class="sxs-lookup"><span data-stu-id="1ea37-117">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="1ea37-118">Conservez les fichiers de sauvegarde où ils seront disponibles, au cas où vous devriez restaurer les données.</span><span class="sxs-lookup"><span data-stu-id="1ea37-118">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="1ea37-119">Planifiez et planifiez les tests périodiques des processus de restauration pris en charge par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1ea37-119">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="1ea37-120">Validez vos processus de sauvegarde et de restauration à l’avance afin de vous assurer qu’ils fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="1ea37-120">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="1ea37-121">Meilleures pratiques pour limiter l’impact d’un sinistre</span><span class="sxs-lookup"><span data-stu-id="1ea37-121">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="1ea37-122">La meilleure stratégie pour traiter les interruptions de service désastreuses (dues à des événements non gérables, tels que des coupures de courant ou des pannes matérielles soudaines), est de supposer qu’elles se produiront et de planifier en conséquence.</span><span class="sxs-lookup"><span data-stu-id="1ea37-122">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="1ea37-123">Si les services Lync, avec un minimum de perturbation et de panne, sont essentiels pour l’entreprise, vous devez envisager d’implémenter des pools de serveurs frontaux couplés, comme décrit dans la rubrique [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="1ea37-123">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="1ea37-124">Ensuite, si l’un de ces pools rencontre un problème, un administrateur peut faire en sorte que les utilisateurs de ce pool soient pris en charge par l’autre pool, avec un minimum de temps d’arrêt.</span><span class="sxs-lookup"><span data-stu-id="1ea37-124">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="1ea37-125">Les plans de gestion des sinistres que vous développez dans le cadre de votre stratégie de sauvegarde et de restauration doivent inclure les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="1ea37-125">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="1ea37-126">La mise à disposition de vos supports logiciels, ainsi que de vos logiciels et mises à jour de microprogramme, est immédiatement disponible.</span><span class="sxs-lookup"><span data-stu-id="1ea37-126">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="1ea37-127">maintenance d’enregistrements relatifs aux matériels et aux logiciels ;</span><span class="sxs-lookup"><span data-stu-id="1ea37-127">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="1ea37-128">Sauvegarde régulière de vos données et surveillance de l’intégrité de vos sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="1ea37-128">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="1ea37-129">formation du personnel en matière de récupération après incident, documentation des procédures et implémentation d’exercices de simulation de récupération après sinistre ;</span><span class="sxs-lookup"><span data-stu-id="1ea37-129">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="1ea37-130">La mise à disposition de matériel de rechange ou, si vous disposez d’un contrat de niveau de service (SLA), vous devez détenir les fournisseurs de matériel et les fournisseurs pour les remplacements d’invites.</span><span class="sxs-lookup"><span data-stu-id="1ea37-130">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="1ea37-131">séparation des emplacements de vos fichiers journaux de transactions (fichiers .ldf) et des fichiers de base de données (fichiers .mdf).</span><span class="sxs-lookup"><span data-stu-id="1ea37-131">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

