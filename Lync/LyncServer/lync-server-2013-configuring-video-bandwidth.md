---
title: 'Lync Server 2013 : configuration de la bande passante vidéo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed1dfd2e8879776733e6ca6fbd8d6024533ef622
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="024c6-102">Configuration de la bande passante vidéo dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="024c6-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="024c6-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="024c6-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="024c6-104">Lync Server 2013 comprend plusieurs paramètres de gestion de la vidéo pour les appels à deux et les conférences à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="024c6-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="024c6-105">Lorsque vous déployez Lync Server 2013, vous devez évaluer si les paramètres par défaut sont appropriés pour votre organisation et les modifier si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="024c6-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="024c6-p102">Les paramètres décrits dans cette section s’appliquent à la fois aux appels entre deux interlocuteurs et aux conférences entre plusieurs participants. Affichez ou modifiez ces paramètres à l’aide de l’une des applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="024c6-p102">The parameters described in this section apply to both two-party calls and multiparty conferencing. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="024c6-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="024c6-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="024c6-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="024c6-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="024c6-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="024c6-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="024c6-111">Vérifiez les paramètres suivants dans votre stratégie de conférence :</span><span class="sxs-lookup"><span data-stu-id="024c6-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="024c6-112">**VideoBitRateKb**   ce paramètre spécifie la vitesse de transmission vidéo maximale en kilobits par seconde (Kbits/s) utilisée pour la vidéo envoyée par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="024c6-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="024c6-113">La valeur par défaut est de 50 000 Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="024c6-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="024c6-114">Les valeurs valides sont comprises entre 0 et 50 000.</span><span class="sxs-lookup"><span data-stu-id="024c6-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="024c6-115">Ce paramètre s’applique séparément à la vidéo principale et à la vidéo panoramique.</span><span class="sxs-lookup"><span data-stu-id="024c6-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="024c6-116">Exemple : Si vous spécifiez 2000 kbits/s, Lync Server peut envoyer 2000 kbits/s pour le flux vidéo principal et 2000 kbits/s pour le flux vidéo panoramique.</span><span class="sxs-lookup"><span data-stu-id="024c6-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="024c6-117">La bande passante de réseau vidéo maximale pour un point de terminaison Lync 2013 est de 8000 Kbits/s pour la vidéo principale et de 2500 kbits/s pour la vidéo panoramique.</span><span class="sxs-lookup"><span data-stu-id="024c6-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="024c6-118">Ces valeurs maximales ne sont atteintes que si plusieurs vidéos sont reçues ou envoyées.</span><span class="sxs-lookup"><span data-stu-id="024c6-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="024c6-119">Pour plus d’informations, reportez-vous à la section « utilisation du réseau multimédia » dans la <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">bande passante réseau requise pour le trafic multimédia dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="024c6-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="024c6-120">Cette section indique la bande passante maximale et classique du flux vidéo pour toutes les résolutions prises en charge.</span><span class="sxs-lookup"><span data-stu-id="024c6-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="024c6-121">**TotalReceiveVideoBitRateKb**   ce paramètre, qui est nouveau dans Lync Server 2013, spécifie la vitesse de transmission maximale autorisée (en kilobits par seconde) pour tous les flux vidéo reçus par un client.</span><span class="sxs-lookup"><span data-stu-id="024c6-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="024c6-122">En d’autres termes, il indique le total de tous les flux vidéo, à l’exception des flux vidéo panoramiques, qu’un client peut recevoir.</span><span class="sxs-lookup"><span data-stu-id="024c6-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="024c6-123">Par exemple, si vous spécifiez 1 500 Kbits/s, le client peut recevoir jusqu’à 1 500 Kbits/s de vidéo, qui peuvent être constitués de plusieurs flux vidéo ou d’un seul flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="024c6-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="024c6-124">Ce paramètre s’applique uniquement aux clients Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="024c6-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="024c6-p106">La valeur par défaut de **TotalReceiveVideoBitRateKb** est 50 000 Kbits/s. Si le paramètre **EnableMultiviewJoin** de la vue Galerie a la valeur True, **TotalReceiveVideoBitRateKb** ne doit pas être inférieur à 420 Kbits/s. Si le paramètre **EnableMultiviewJoin** de la vue Galerie a la valeur False, **TotalReceiveVideoBitRateKb** ne doit pas être inférieur à 100 Kbits/s. Si **EnableMultiviewJoin** a la valeur True et si la valeur que vous définissez est inférieure à 420 Kbits/s, la valeur seuil est affectée par défaut. Ce seuil permet d’éviter une erreur de configuration involontaire qui pourrait entraîner une mauvaise expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="024c6-p106">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps. If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value. This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="024c6-130">Pour plus d’informations sur le paramètre <STRONG>EnableMultiviewJoin</STRONG> , voir <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="024c6-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="024c6-131">**MaxVideoConferencingResolution**   ce paramètre n’est plus utilisé pour les clients Lync Server 2013 dans les conférences Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="024c6-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="024c6-132">Les conférences Lync Server 2013 utilisent les contrôles de vitesse de transmission décrits plus haut dans cette section.</span><span class="sxs-lookup"><span data-stu-id="024c6-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="024c6-133">Ce paramètre est toujours utilisé pour les clients hérités qui rejoignent une conférence Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="024c6-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="024c6-134">Ce paramètre détermine la résolution maximale autorisée pour les clients hérités dans les conférences organisées par les utilisateurs hébergés sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="024c6-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="024c6-135">Autrement dit, les clients hérités sont traités de la même manière que dans les versions précédentes de Lync Server ou d’Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="024c6-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="024c6-p108">Outre les paramètres de stratégie de conférence qui s’appliquent aux utilisateurs, évaluez les paramètres de configuration multimédia. Affichez ou modifiez ces paramètres à l’aide de l’une des applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="024c6-p108">In addition to conferencing policy settings that apply to users, evaluate media configuration settings. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="024c6-138">**Get-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="024c6-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="024c6-139">**Set-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="024c6-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="024c6-140">**New-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="024c6-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="024c6-141">Vérifiez le paramètre suivant :</span><span class="sxs-lookup"><span data-stu-id="024c6-141">Verify the following setting:</span></span>

  - <span data-ttu-id="024c6-142">**MaxVideoRateAllowed**   ce paramètre par pool spécifie le débit maximal auquel les signaux vidéo seront transférés aux points de terminaison du client.</span><span class="sxs-lookup"><span data-stu-id="024c6-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="024c6-143">Il s’applique uniquement aux versions précédentes des clients Lync Server.</span><span class="sxs-lookup"><span data-stu-id="024c6-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="024c6-144">Les clients Lync Server 2013 ignorent ce paramètre et utilisent à la place le paramètre TotalReceiveVideoBitRateKb dans la stratégie de conférence.</span><span class="sxs-lookup"><span data-stu-id="024c6-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="024c6-p110">La valeur par défaut est HD720P. Les valeurs valides sont HD720p15M, VGA600K et CIF250K.</span><span class="sxs-lookup"><span data-stu-id="024c6-p110">The default value is HD720P. Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="024c6-147">Exemple : si vous spécifiez 1 500 Kbits/s, tous les clients hérités du pool peuvent recevoir jusqu’à 1 500 Kbits/s de vidéo lors des conférences entre deux interlocuteurs et plus.</span><span class="sxs-lookup"><span data-stu-id="024c6-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="024c6-148">Les procédures suivantes sont des exemples d’utilisation de Lync Server Management Shell pour modifier les paramètres décrits dans cette section.</span><span class="sxs-lookup"><span data-stu-id="024c6-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="024c6-149">Pour modifier la stratégie de conférence des paramètres vidéo</span><span class="sxs-lookup"><span data-stu-id="024c6-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="024c6-150">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="024c6-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="024c6-151">À partir de la ligne de commande, exécutez l’applet de commande suivante pour modifier la stratégie de conférence :</span><span class="sxs-lookup"><span data-stu-id="024c6-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="024c6-152">Pour modifier la configuration multimédia des clients hérités</span><span class="sxs-lookup"><span data-stu-id="024c6-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="024c6-153">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="024c6-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="024c6-154">À partir de la ligne de commande, exécutez l’applet de commande suivante pour modifier la configuration multimédia :</span><span class="sxs-lookup"><span data-stu-id="024c6-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

