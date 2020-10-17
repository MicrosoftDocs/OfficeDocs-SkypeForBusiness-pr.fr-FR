---
title: Contrôle d’admission des appels avec une passerelle PSTN ou un PBX tiers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7abd33af2dd2a7a5858fd8b888201b6471d0cf9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502811"
---
# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="33f40-102">Contrôle d’admission des appels dans Lync Server 2013 avec une passerelle PSTN ou un PBX tiers</span><span class="sxs-lookup"><span data-stu-id="33f40-102">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33f40-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="33f40-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="33f40-104">Cette rubrique décrit des exemples de déploiement du contrôle d’admission des appels sur la liaison entre l’interface de la passerelle du serveur de médiation et une passerelle RTC (réseau téléphonique commuté) ou un PBX (Private Branch Exchange) tiers.</span><span class="sxs-lookup"><span data-stu-id="33f40-104">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="33f40-105">Cas 1 : contrôle d’admission des appels entre le serveur de médiation et une passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="33f40-105">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="33f40-106">Le contrôle d’admission des appels peut être déployé sur la liaison de réseau étendu depuis l’interface de passerelle du serveur de médiation vers une passerelle PSTN ou PBX tierce.</span><span class="sxs-lookup"><span data-stu-id="33f40-106">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="33f40-107">**Cas 1 : contrôle d’admission des appels entre le serveur de médiation et une passerelle PSTN**</span><span class="sxs-lookup"><span data-stu-id="33f40-107">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="33f40-108">![Cas 1 : CAC entre la passerelle PSTN de serveur de médiation](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Cas 1 : CAC entre la passerelle PSTN de serveur de médiation")</span><span class="sxs-lookup"><span data-stu-id="33f40-108">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="33f40-109">Dans cet exemple, le contrôle d’admission des appels est appliqué entre le serveur de médiation et une passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="33f40-109">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="33f40-110">Si un utilisateur de client Lync sur le site réseau 1 passe un appel RTC via la passerelle PSTN dans le site réseau 2, le média transite par la liaison WAN.</span><span class="sxs-lookup"><span data-stu-id="33f40-110">If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="33f40-111">Par conséquent, deux vérifications de contrôle d’admission des appels sont effectuées pour chaque session PSTN :</span><span class="sxs-lookup"><span data-stu-id="33f40-111">Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="33f40-112">Entre l’application cliente Lync et le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="33f40-112">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="33f40-113">Entre le serveur de médiation et la passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="33f40-113">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="33f40-114">Cela fonctionne pour les appels RTC entrants vers un client dans le site réseau 1 et pour les appels RTC sortants provenant d’une application cliente dans le site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="33f40-114">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="33f40-115">Assurez-vous que le sous-réseau IP auquel appartient la passerelle PSTN est configuré et associé au site réseau 2.</span><span class="sxs-lookup"><span data-stu-id="33f40-115">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="33f40-116">Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation est configuré et associé au site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="33f40-116">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="33f40-117">Pour plus d’informations, consultez <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">la rubrique associer un sous-réseau à un site réseau dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="33f40-117">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="33f40-118">Cas 2 : CAC entre le serveur de médiation et un PBX tiers avec point de terminaison multimédia</span><span class="sxs-lookup"><span data-stu-id="33f40-118">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="33f40-119">Cette configuration est semblable au cas 1.</span><span class="sxs-lookup"><span data-stu-id="33f40-119">This configuration is similar to Case 1.</span></span> <span data-ttu-id="33f40-120">Dans les deux cas, le serveur de médiation sait quel périphérique termine le média à l’extrémité opposée de la liaison de réseau étendu, et l’adresse IP de la passerelle PSTN ou du PBX avec le point de terminaison multimédia (MTP) est configurée sur le serveur de médiation comme tronçon suivant.</span><span class="sxs-lookup"><span data-stu-id="33f40-120">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="33f40-121">**Cas 2 : CAC entre le serveur de médiation et un PBX tiers avec MTP**</span><span class="sxs-lookup"><span data-stu-id="33f40-121">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="33f40-122">![Cas 2 : CAC entre PBX de serveur de médiation avec MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Cas 2 : CAC entre PBX de serveur de médiation avec MTP")</span><span class="sxs-lookup"><span data-stu-id="33f40-122">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="33f40-123">Dans cet exemple, CAC est appliqué entre le serveur de médiation et le PBX/MTP.</span><span class="sxs-lookup"><span data-stu-id="33f40-123">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="33f40-124">Si un utilisateur client Lync sur le site réseau 1 passe un appel RTC via le PBX/MTP situé dans le site réseau 2, le média transite par la liaison de réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="33f40-124">If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="33f40-125">Par conséquent, pour chaque session RTC, deux vérifications de contrôle d’admission des appels sont effectuées :</span><span class="sxs-lookup"><span data-stu-id="33f40-125">Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="33f40-126">Entre l’application cliente Lync et le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="33f40-126">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="33f40-127">Entre le serveur de médiation et le PBX/MTP</span><span class="sxs-lookup"><span data-stu-id="33f40-127">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="33f40-128">Cela fonctionne pour les appels RTC entrants vers un client dans le site réseau 1 et les appels RTC sortants provenant d’un client dans le site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="33f40-128">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="33f40-129">Assurez-vous que le sous-réseau IP auquel appartient le MTP est configuré et associé au site réseau 2.</span><span class="sxs-lookup"><span data-stu-id="33f40-129">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="33f40-130">Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation est configuré et associé au site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="33f40-130">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="33f40-131">Pour plus d’informations, consultez <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">la rubrique associer un sous-réseau à un site réseau dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="33f40-131">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="33f40-132">Cas 3 : CAC entre le serveur de médiation et un système PBX tiers sans point de terminaison multimédia</span><span class="sxs-lookup"><span data-stu-id="33f40-132">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="33f40-133">Le cas 3 est légèrement différent des deux premiers cas.</span><span class="sxs-lookup"><span data-stu-id="33f40-133">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="33f40-134">S’il n’y a pas de MTP sur le PBX tiers, pour une demande de session sortante adressée au PBX tiers, le serveur de médiation ne sait pas où le média se termine dans la limite du PBX.</span><span class="sxs-lookup"><span data-stu-id="33f40-134">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="33f40-135">Dans ce cas, le média est directement acheminé entre le serveur de médiation et le périphérique de point de terminaison tiers.</span><span class="sxs-lookup"><span data-stu-id="33f40-135">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="33f40-136">**Cas 3 : CAC entre le serveur de médiation et un PBX tiers sans MTP**</span><span class="sxs-lookup"><span data-stu-id="33f40-136">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="33f40-137">![Cas 3 : CAC entre PBX de serveur de médiation sans MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Cas 3 : CAC entre PBX de serveur de médiation sans MTP")</span><span class="sxs-lookup"><span data-stu-id="33f40-137">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="33f40-138">Dans cet exemple, si un utilisateur de client Lync sur le site réseau 1 passe un appel à un utilisateur via le PBX, le serveur de médiation peut effectuer des vérifications CAC uniquement sur la jambe proxy (entre l’application cliente Lync et le serveur de médiation).</span><span class="sxs-lookup"><span data-stu-id="33f40-138">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server).</span></span> <span data-ttu-id="33f40-139">Étant donné que le serveur de médiation n’a pas d’informations sur l’appareil de point de terminaison pendant que la session est demandée, les vérifications du contrôle d’admission des appels ne peuvent pas être effectuées sur la liaison de réseau étendu (entre le serveur de médiation et le point de terminaison tiers) avant l’établissement de l’appel.</span><span class="sxs-lookup"><span data-stu-id="33f40-139">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="33f40-140">Une fois la session établie, le serveur de médiation facilite la comptabilisation de la bande passante utilisée sur la jonction.</span><span class="sxs-lookup"><span data-stu-id="33f40-140">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="33f40-141">Pour les appels qui proviennent du point de terminaison tiers, les informations relatives à ce périphérique de point de terminaison sont disponibles au moment de la demande de session et la vérification du contrôle d’admission des appels peut être effectuée sur les deux côtés du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="33f40-141">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="33f40-142">Assurez-vous que le sous-réseau IP auquel appartiennent les périphériques de point de terminaison est configuré et associé au site réseau 2.</span><span class="sxs-lookup"><span data-stu-id="33f40-142">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="33f40-143">Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation est configuré et associé au site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="33f40-143">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="33f40-144">Pour plus d’informations, consultez <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">la rubrique associer un sous-réseau à un site réseau dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="33f40-144">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

