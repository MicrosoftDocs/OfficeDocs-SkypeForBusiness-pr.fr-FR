---
title: 'Lync Server 2013 : meilleures pratiques pour le contrôle d’admission des appels'
description: 'Lync Server 2013 : meilleures pratiques pour le contrôle d’admission des appels.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c32af904dc7fb48a1a5d1903bd6ed1f81f4cb3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552130"
---
# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="5bf4b-103">Meilleures pratiques pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bf4b-103">Best practices for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bf4b-104">_**Dernière modification de la rubrique :** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="5bf4b-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="5bf4b-105">Pour améliorer les performances et faciliter le déploiement, appliquez les meilleures pratiques suivantes lorsque vous déployez le contrôle d’admission des appels :</span><span class="sxs-lookup"><span data-stu-id="5bf4b-105">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="5bf4b-106">Assurez-vous que les réseaux étendus (WAN) sont correctement configurés pour le trafic multimédia actuel et prévu.</span><span class="sxs-lookup"><span data-stu-id="5bf4b-106">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5bf4b-107">Nous vous recommandons de factoriser un tampon vers vos limites de bande passante.</span><span class="sxs-lookup"><span data-stu-id="5bf4b-107">We recommend that you factor in a buffer to your bandwidth limits.</span></span> <span data-ttu-id="5bf4b-108">Certains scénarios, tels que les conditions de concurrence, affectent la bande passante totale utilisée et peuvent entraîner des situations dans lesquelles la limite de bande passante est dépassée.</span><span class="sxs-lookup"><span data-stu-id="5bf4b-108">There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded.</span></span> <span data-ttu-id="5bf4b-109">Par exemple, si deux appels essaient de démarrer alors que le trafic multimédia approche de la limite de bande passante, l’un d’entre eux peut être refusé, car l’autre a pu démarrer en premier.</span><span class="sxs-lookup"><span data-stu-id="5bf4b-109">For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="5bf4b-110">Surveillez l’utilisation du réseau et les enregistrements des détails des appels afin de pouvoir choisir les paramètres CAC optimaux et mettre à jour les paramètres CAC lorsque les modifications de l’utilisation du réseau</span><span class="sxs-lookup"><span data-stu-id="5bf4b-110">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="5bf4b-111">Utilisez les stratégies de bande passante CAC pour compléter les paramètres QoS.</span><span class="sxs-lookup"><span data-stu-id="5bf4b-111">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="5bf4b-112">Si vous souhaitez réacheminer les appels bloqués vers le réseau téléphonique commuté, vérifiez la capacité et la fonctionnalité PSTN.</span><span class="sxs-lookup"><span data-stu-id="5bf4b-112">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="5bf4b-113">Pour plus d’informations, consultez la rubrique [planification de l’acheminement des communications vocales dans Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="5bf4b-113">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5bf4b-114">La capacité fait référence au nombre de ports que vous devez ouvrir afin de prendre en charge un éventuel réacheminement RTC.</span><span class="sxs-lookup"><span data-stu-id="5bf4b-114">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

