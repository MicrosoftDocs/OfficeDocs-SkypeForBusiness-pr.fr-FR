---
title: 'Lync Server 2013 : conditions préalables à la sauvegarde pour le basculement du pool ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a23e93741400efe4744e9219a19ca2c0217a33e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="05587-102">Conditions préalables à la sauvegarde pour le basculement du pool ABC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05587-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05587-103">_**Dernière modification de la rubrique :** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="05587-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="05587-104">Pour tirer le meilleur parti de la procédure de basculement de pool ABC, vous devez effectuer certaines sauvegardes avant le basculement et le basculement :</span><span class="sxs-lookup"><span data-stu-id="05587-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="05587-105">Vous devez sauvegarder régulièrement les données de configuration de LIS (location Information Service) à partir du pool A à l’aide de la cmdlet **Export-CsLISConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="05587-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="05587-106">Vous devez sauvegarder régulièrement les données de configuration du groupe Response Group dans le pool A à l’aide de la cmdlet **Export-applet csrgsconfiguration** .</span><span class="sxs-lookup"><span data-stu-id="05587-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="05587-107">En règle générale, nous vous recommandons d’effectuer des sauvegardes quotidiennes, mais si le volume de vos changements est élevé, vous pouvez planifier des sauvegardes plus fréquentes.</span><span class="sxs-lookup"><span data-stu-id="05587-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="05587-108">La quantité d’informations que vous pouvez perdre en cas de sinistre dépend de la fréquence de vos sauvegardes, ainsi que de la fréquence et du volume des modifications.</span><span class="sxs-lookup"><span data-stu-id="05587-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="05587-109">L’application Response Group ne peut stocker qu’un seul ensemble de paramètres au niveau de l’application par pool.</span><span class="sxs-lookup"><span data-stu-id="05587-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="05587-110">Ces paramètres sont accessibles via les cmdlets **Get-applet csrgsconfiguration** .</span><span class="sxs-lookup"><span data-stu-id="05587-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="05587-111">Les paramètres incluent la configuration de l’attente musicale par défaut, le fichier audio de l’attente musicale par défaut, la période de grâce de l’agent de grâce et la configuration du contexte de l’appel.</span><span class="sxs-lookup"><span data-stu-id="05587-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="05587-112">Ces paramètres peuvent être transférés d’un pool à un autre via l’applet de commande **Import-applet csrgsconfiguration** à l’aide du paramètre **ReplaceExistingSettings** , mais cette opération remplace tous les paramètres au niveau de l’application dans le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="05587-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="05587-113">À un emplacement distinct, conservez une copie de sauvegarde de tous les fichiers audio d’origine qui ont été utilisés pour configurer l’application Response Group (c’est-à-dire, tous les enregistrements ou les fichiers de conservation de musique).</span><span class="sxs-lookup"><span data-stu-id="05587-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="05587-114">Si vous avez des fichiers de mise en attente musicale personnalisés qui ont été téléchargés pour le parcage d’appel dans un pool, vous devez conserver une copie de ces fichiers dans un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="05587-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="05587-115">Ces fichiers ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence de Lync Server 2013 et ils seront perdus si les fichiers chargés dans le pool sont endommagés, endommagés ou effacés.</span><span class="sxs-lookup"><span data-stu-id="05587-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="05587-116">L’application de parcage d’appel ne peut stocker qu’un seul ensemble de paramètres et un fichier audio de mise en attente musicale personnalisé par pool.</span><span class="sxs-lookup"><span data-stu-id="05587-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="05587-117">Ces paramètres sont accessibles via la cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="05587-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="05587-118">Étant donné que le mécanisme de récupération d’urgence pour le parcage d’appel repose sur l’application de parcage d’appel du pool de sauvegarde, les paramètres du pool principal ne sont ni sauvegardés ni conservés en cas de sinistre.</span><span class="sxs-lookup"><span data-stu-id="05587-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="05587-119">Si le pool principal est perdu, ces paramètres ne peuvent pas être récupérés et lorsqu’un nouveau pool est déployé pour remplacer le pool principal, les paramètres de parcage d’appel et tout fichier audio de l’attente musicale personnalisé doivent être reconfigurés.</span><span class="sxs-lookup"><span data-stu-id="05587-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="05587-120">Si vous configurez des annonces dans le cadre de la fonctionnalité de voix numérique non affectée, nous vous recommandons de conserver dans un autre emplacement une copie de tous les fichiers audio d’origine utilisés lors de la configuration initiale.</span><span class="sxs-lookup"><span data-stu-id="05587-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="05587-121">Si vous n’avez pas effectué cette opération, vous pouvez obtenir une copie des fichiers audio configurés dans le magasin de fichiers du serveur ou du pool vers lequel les fichiers audio ont été importés.</span><span class="sxs-lookup"><span data-stu-id="05587-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="05587-122">Ces fichiers ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence de Lync Server 2013 et ils seront perdus si les fichiers chargés dans le pool sont endommagés, endommagés ou effacés.</span><span class="sxs-lookup"><span data-stu-id="05587-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="05587-123">Pour copier tous les fichiers audio utilisés pour configurer la fonctionnalité de voix numérique non attribué à partir du magasin de fichiers d’un serveur ou d’un pool, utilisez :</span><span class="sxs-lookup"><span data-stu-id="05587-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="05587-124">Si vous avez des bases de données de surveillance et d’archivage dans un pool, vous devez utiliser les outils de gestion SQL Server pour les sauvegarder.</span><span class="sxs-lookup"><span data-stu-id="05587-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="05587-125">Dans la procédure de basculement ABC, les bases de données de surveillance et d’archivage ne sont pas conservées si elles sont colocalisées dans le pool A, car ces bases de données ne sont pas sauvegardées via le service de sauvegarde Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05587-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

