---
title: 'Lync Server 2013 : Planification de la récupération d’urgence pour le parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7da940f55574e1c6d50aeb06c0c80710bdbaad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="0ff73-102">Planification de la récupération d’urgence pour le parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ff73-102">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ff73-103">_**Dernière modification de la rubrique:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="0ff73-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="0ff73-104">Cette section décrit quelques méthodes de préparation de l’application de parc d’appels à des fins de reprise après sinistre et des éléments à prendre en compte lors du processus de reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="0ff73-104">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="0ff73-105">Préparation de la reprise après sinistre du parc d’appels</span><span class="sxs-lookup"><span data-stu-id="0ff73-105">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="0ff73-106">Gardez les points suivants à l’esprit lorsque vous préparez et mettez en oeuvre des procédures de reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="0ff73-106">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="0ff73-107">Prévoyez une reprise après sinistre lors de la planification de la capacité.</span><span class="sxs-lookup"><span data-stu-id="0ff73-107">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="0ff73-108">Pour la capacité de reprise après sinistre, chaque pool dans un pool couplé doit être capable de gérer les charges de travail des services de parc d’appels dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="0ff73-108">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="0ff73-109">Pour plus d’informations sur la planification de la capacité de parc d’appels, voir [planification de la capacité pour le parc d’appels dans Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span><span class="sxs-lookup"><span data-stu-id="0ff73-109">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="0ff73-110">Lors de la récupération d’urgence, les utilisateurs qui ont été redirigés vers le pool de sauvegarde dans le cadre du processus de basculement utilisent le service de parc d’appels qui s’exécute dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0ff73-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="0ff73-111">Par conséquent, la prise en charge du parc d’appels lors d’une reprise après sinistre nécessite que l’application du parc d’appels soit déployée et activée dans le pool principal et dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0ff73-111">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="0ff73-112">Chaque liste doit avoir une plage de numéros en orbite valide pour les utilisateurs qui sont dans le groupe, à utiliser pour les appels en stationnement.</span><span class="sxs-lookup"><span data-stu-id="0ff73-112">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="0ff73-113">Conservez toujours une copie de sauvegarde séparée de tout morceau de musique personnalisé en attente qui a été téléchargé pour le parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="0ff73-113">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="0ff73-114">Ces fichiers ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence de Lync Server 2013 et seront perdus si les fichiers téléchargés vers le pool sont endommagés, endommagés ou supprimés.</span><span class="sxs-lookup"><span data-stu-id="0ff73-114">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="0ff73-115">Considérations en matière de reprise après sinistre du parc d’appels</span><span class="sxs-lookup"><span data-stu-id="0ff73-115">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="0ff73-116">Vous ne pouvez définir qu’un seul ensemble de paramètres de configuration d’application de parc d’appels et un seul fichier audio de musique personnalisé par liste.</span><span class="sxs-lookup"><span data-stu-id="0ff73-116">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="0ff73-117">Ces paramètres incluent le seuil de temporisation, la musique en attente, les tentatives de sélection d’appels maximum et l’URI de délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="0ff73-117">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="0ff73-118">Pour afficher ces paramètres de configuration, exécutez l’applet **de passe Get-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0ff73-118">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="0ff73-119">Pour plus d’informations sur l’applet de connexion **Get-CsCpsConfiguration** , voir [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0ff73-119">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="0ff73-120">En cas de reprise après sinistre, le parc d’appels utilise l’application de parc d’appels dans le pool de sauvegarde, de sorte que les paramètres du pool principal ne soient pas sauvegardés.</span><span class="sxs-lookup"><span data-stu-id="0ff73-120">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="0ff73-121">Si le pool principal ne peut pas être récupéré et que vous déployez un nouveau pool pour remplacer le pool principal, les paramètres du pool principal sont perdus et vous devez reconfigurer les paramètres de parc d’appels et les fichiers audio de la musique personnalisée dans le nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="0ff73-121">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="0ff73-122">Si vous déployez un nouveau pool avec un nom de domaine complet différent (FQDN) pour remplacer le pool principal, vous devez réaffecter toutes les plages d’orbite de parking d’appel associées au pool principal au FQDN du nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="0ff73-122">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="0ff73-123">Pour réattribuer des plages d’Orbit à la nouvelle liste de choix, vous pouvez utiliser le panneau de configuration de Lync Server ou l’applet **de commande Set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="0ff73-123">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="0ff73-124">Pour plus d’informations sur l’applet **de connexion Set-CsCallParkOrbit** , reportez-vous à [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="0ff73-124">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

