---
title: 'Lync Server 2013: meilleures pratiques pour la sauvegarde et la restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc7a926bd8fd5c61f87d5e8252c30f40e5a6a69
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="25347-102">Recommandations en matière de sauvegarde et de restauration pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25347-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25347-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="25347-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="25347-104">Cette section inclut deux types de meilleures pratiques:</span><span class="sxs-lookup"><span data-stu-id="25347-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="25347-105">Pratiques recommandées pour la sauvegarde et la restauration.</span><span class="sxs-lookup"><span data-stu-id="25347-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="25347-106">Recommandations permettant de réduire l’impact d’un sinistre.</span><span class="sxs-lookup"><span data-stu-id="25347-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="25347-107">Recommandations en matière de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="25347-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="25347-108">Pour faciliter votre processus de sauvegarde et de restauration, appliquez les meilleures pratiques suivantes lors de la sauvegarde ou de la restauration de vos données:</span><span class="sxs-lookup"><span data-stu-id="25347-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="25347-109">Effectuez des sauvegardes régulières à intervalles appropriés.</span><span class="sxs-lookup"><span data-stu-id="25347-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="25347-110">Le plus simple et le plus souvent utilisé dans les plannings de type et de rotation est une sauvegarde complète et nocturne de l’ensemble de la base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25347-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="25347-111">Si une restauration est nécessaire, le processus de restauration ne nécessite qu’une seule sauvegarde et aucune donnée de jour ne doit être perdue.</span><span class="sxs-lookup"><span data-stu-id="25347-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="25347-112">Si vous utilisez des cmdlets ou le panneau de configuration de Lync Server pour apporter des modifications de configuration, utilisez l’applet de commande **Export-CsConfiguration** pour effectuer une sauvegarde de capture instantanée du fichier de configuration de la topologie (XDS. mdf) après avoir effectué les modifications, afin de ne pas perdre les modifications si vous devez restaurer vos bases de données.</span><span class="sxs-lookup"><span data-stu-id="25347-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="25347-113">Notez que cette configuration est sauvegardée au format XML et compactée sous forme de fichier ZIP.</span><span class="sxs-lookup"><span data-stu-id="25347-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="25347-114">Assurez-vous que le dossier partagé que vous envisagez d’utiliser pour la sauvegarde de Lync Server dispose de suffisamment d’espace disque pour contenir toutes les données sauvegardées.</span><span class="sxs-lookup"><span data-stu-id="25347-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="25347-115">Planifier des sauvegardes lorsque la consommation de Lync Server est généralement faible, afin d’améliorer les performances du serveur et l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="25347-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="25347-116">Assurez-vous que l’emplacement de sauvegarde des données est sécurisé (nous vous recommandons d’utiliser un emplacement distant).</span><span class="sxs-lookup"><span data-stu-id="25347-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="25347-117">Conservez les fichiers de sauvegarde dans lesquels ils seront disponibles, si vous avez besoin de restaurer les données.</span><span class="sxs-lookup"><span data-stu-id="25347-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="25347-118">Planifiez et planifiez des tests périodiques des processus de restauration pris en charge par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="25347-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="25347-119">Validez vos processus de sauvegarde et de restauration à l’avance pour vérifier qu’ils fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="25347-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="25347-120">Recommandations pour réduire l’impact d’un sinistre</span><span class="sxs-lookup"><span data-stu-id="25347-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="25347-121">La meilleure stratégie pour gérer les interruptions de service désastreuses (provoquées par des événements ingérables tels que les coupures de courant ou les défaillances matérielles soudaines) est de supposer qu’elles se produiront et de planifier en conséquence.</span><span class="sxs-lookup"><span data-stu-id="25347-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="25347-122">Si les services Lync, présentant un minimum de perturbation et d’interruption de service, sont vitaux pour votre organisation, il est recommandé de mettre en œuvre des pools de serveurs frontaux couplés, comme décrit dans la section [planification de la haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="25347-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="25347-123">Ensuite, si l’une de ces réserves rencontre un problème, un administrateur peut basculer les utilisateurs de ce pool pour qu’ils soient desservis par l’autre réserve, avec un minimum de temps d’arrêt.</span><span class="sxs-lookup"><span data-stu-id="25347-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="25347-124">Les plans de gestion des sinistres développés dans le cadre de votre stratégie de sauvegarde et de restauration doivent inclure les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="25347-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="25347-125">La conservation de votre média logiciel ainsi que des mises à jour de logiciels et de microprogrammes, facilement disponibles.</span><span class="sxs-lookup"><span data-stu-id="25347-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="25347-126">Maintenance des enregistrements matériels et logiciels.</span><span class="sxs-lookup"><span data-stu-id="25347-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="25347-127">Sauvegarder vos données régulièrement et surveiller l’intégrité de vos sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="25347-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="25347-128">Formation de votre équipe dans le cas d’une reprise après sinistre, de procédures de documentation et de l’implémentation de perçages de simulation de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="25347-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="25347-129">La conservation de matériel de réserve ou, si vous disposez d’un contrat de niveau de service (SLA), un contrat avec des fournisseurs de matériel et des fournisseurs pour les remplacements d’instructions.</span><span class="sxs-lookup"><span data-stu-id="25347-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="25347-130">Séparation de l’emplacement de vos fichiers journaux de transactions (fichiers. ldf) et fichiers de base de données (fichiers. mdf).</span><span class="sxs-lookup"><span data-stu-id="25347-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

