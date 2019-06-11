---
title: 'Lync Server 2013 : Meilleures pratiques liées au contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89be654a01615c750ce4f49f866e9339bc7e261
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="35d5e-102">Meilleures pratiques liées au contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35d5e-102">Best practices for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35d5e-103">_**Dernière modification de la rubrique:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="35d5e-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="35d5e-104">Pour améliorer les performances et faciliter le déploiement, appliquez les recommandations suivantes lors du déploiement du contrôle d’admission des appels :</span><span class="sxs-lookup"><span data-stu-id="35d5e-104">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="35d5e-105">Vérifiez que les réseaux étendus (WAN) sont configurés en conséquence pour le trafic multimédia actuel et envisagé.</span><span class="sxs-lookup"><span data-stu-id="35d5e-105">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35d5e-p101">Nous vous conseillons de définir un facteur en mémoire tampon quant aux limites de votre bande passante. Il existe des scénarios de condition de concurrence qui agissent sur la bande passante totale utilisée et qui peuvent entraîner des situations de dépassement de la limite de la bande. Prenons l’exemple de deux appels amorcés alors que le trafic multimédia approche de la limite de la bande passante : l’un des appels pourra être refusé, car l’autre a été configuré pour démarrer en premier.</span><span class="sxs-lookup"><span data-stu-id="35d5e-p101">We recommend that you factor in a buffer to your bandwidth limits. There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded. For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="35d5e-109">Contrôlez l’utilisation du réseau et les enregistrements des détails des appels pour pouvoir choisir les meilleurs paramètres de contrôle d’admission des appels (CAC) et les mettre à jour en fonction de l’évolution de l’utilisation du réseau.</span><span class="sxs-lookup"><span data-stu-id="35d5e-109">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="35d5e-110">Utilisez les stratégies de bande passante CAC pour compléter les paramètres QoS.</span><span class="sxs-lookup"><span data-stu-id="35d5e-110">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="35d5e-111">Si vous souhaitez réacheminer des appels bloqués sur le réseau RTC, vérifiez les fonctionnalités et capacités correspondantes.</span><span class="sxs-lookup"><span data-stu-id="35d5e-111">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="35d5e-112">Pour plus d’informations, reportez-vous à la [planification du routage de la voix sortante dans Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="35d5e-112">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35d5e-113">La capacité fait référence au nombre de ports à ouvrir pour prendre en charge un éventuel réacheminement vers le réseau RTC.</span><span class="sxs-lookup"><span data-stu-id="35d5e-113">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

