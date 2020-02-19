---
title: 'Lync Server 2013 : planification de la récupération d’urgence du parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca9eb8b87d4485fe1cb02aa8663b362d921a4fff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="d54d9-102">Planification de la récupération d’urgence par le parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d54d9-102">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d54d9-103">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="d54d9-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="d54d9-104">Cette section décrit certaines façons de préparer l’application de parcage d’appel pour la récupération d’urgence et quelques considérations pour le processus de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="d54d9-104">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="d54d9-105">Préparation de la récupération d’urgence du parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="d54d9-105">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="d54d9-106">Gardez les informations suivantes à l’esprit lorsque vous préparez et menez à bien les procédures de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="d54d9-106">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="d54d9-107">Planifiez la récupération d’urgence lorsque vous effectuez votre planification de capacité.</span><span class="sxs-lookup"><span data-stu-id="d54d9-107">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="d54d9-108">Pour la capacité de récupération d’urgence, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail des services de parcage d’appel dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="d54d9-108">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="d54d9-109">Pour plus d’informations sur la planification de la capacité du parcage d’appel, voir [Capacity Planning for Call parcage in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span><span class="sxs-lookup"><span data-stu-id="d54d9-109">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="d54d9-110">Durant la récupération d’urgence, les utilisateurs redirigés vers le pool de sauvegarde durant le processus de basculement utilisent le service de parcage d’appel exécuté dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d54d9-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="d54d9-111">Par conséquent, la prise en charge du parcage d’appel pendant la récupération d’urgence nécessite le déploiement et l’activation de l’application de parcage d’appel dans le pool principal et le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d54d9-111">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="d54d9-112">Chaque pool doit avoir une plage de numéros d’orbite valable pour que les utilisateurs hébergés dans ce pool puissent utiliser le parcage d’appels.</span><span class="sxs-lookup"><span data-stu-id="d54d9-112">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="d54d9-113">Conservez toujours une copie de sauvegarde distincte de toute musique personnalisée en conservation qui a été téléchargée pour le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="d54d9-113">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="d54d9-114">Ces fichiers ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence de Lync Server 2013 et seront perdus si les fichiers chargés vers le pool sont endommagés, endommagés ou effacés.</span><span class="sxs-lookup"><span data-stu-id="d54d9-114">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="d54d9-115">Considérations relatives à la récupération d’urgence du parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="d54d9-115">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="d54d9-116">Vous ne pouvez définir qu’un seul ensemble de paramètres de configuration de l’application de parcage d’appel et un seul fichier audio de mise en attente musicale personnalisé par pool.</span><span class="sxs-lookup"><span data-stu-id="d54d9-116">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="d54d9-117">Ces paramètres incluent le seuil d’expiration, la musique d’attente, le nombre maximum de tentatives de prises d’appels, et l’URI d’expiration.</span><span class="sxs-lookup"><span data-stu-id="d54d9-117">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="d54d9-118">Pour afficher ces paramètres de configuration, exécutez la cmdlet **Get-CsCpsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d54d9-118">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="d54d9-119">Pour plus d’informations sur la cmdlet **Get-CsCpsConfiguration** , voir [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="d54d9-119">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="d54d9-120">Pendant la récupération d’urgence, le parcage d’appel utilise l’application de parcage d’appel dans le pool de sauvegarde, de sorte que les paramètres du pool principal ne sont pas sauvegardés.</span><span class="sxs-lookup"><span data-stu-id="d54d9-120">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="d54d9-121">Si le pool principal ne peut pas être récupéré et si vous déployez un nouveau pool pour remplacer le pool principal, les paramètres du pool principal sont perdus et vous devez reconfigurer les paramètres de parcage d’appel et tous les fichiers audio de la musique personnalisée dans le nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="d54d9-121">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="d54d9-122">Si vous déployez un nouveau pool avec un nom de domaine complet (FQDN) différent pour remplacer le pool principal, vous devez réaffecter toutes les plages d’orbites de parcage d’appel associées au pool principal au nom de domaine complet du nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="d54d9-122">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="d54d9-123">Pour réaffecter les plages d’orbites au nouveau pool, vous pouvez utiliser le panneau de configuration Lync Server ou la cmdlet **Set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="d54d9-123">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="d54d9-124">Pour plus d’informations sur l’applet de commande **Set-CsCallParkOrbit** , voir [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="d54d9-124">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

