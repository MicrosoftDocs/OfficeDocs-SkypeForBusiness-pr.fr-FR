---
title: 'Lync Server 2013 : configuration DNS requise pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ceddef859ebc24168c12fdf0721448c6d2b658
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="81144-102">Configuration DNS requise pour la mobilité avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81144-102">DNS requirements for mobility with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81144-103">_**Dernière modification de la rubrique :** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="81144-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="81144-104">Lorsque vous déployez la fonctionnalité de mobilité Lync Server 2013, vous pouvez utiliser les nouvelles URL disponibles avec le service de découverte automatique Microsoft Lync Server 2013 ou vous pouvez utiliser vos URL de services Web existantes.</span><span class="sxs-lookup"><span data-stu-id="81144-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="81144-105">Si vous utilisez vos URL existantes, les utilisateurs doivent entrer manuellement les URL dans les paramètres de leur appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="81144-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="81144-106">Cette option est généralement utilisée à des fins de dépannage.</span><span class="sxs-lookup"><span data-stu-id="81144-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="81144-107">Lorsque vous utilisez les nouvelles URL, les clients mobiles peuvent découvrir automatiquement les ressources Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81144-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="81144-108">Lorsque vous prenez en charge la découverte automatique, vous devez ajouter de nouveaux enregistrements DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="81144-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="81144-109">Cette section décrit les enregistrements DNS nécessaires pour la découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="81144-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="81144-110">Pour prendre en charge la découverte automatique, vous devez créer les enregistrements DNS suivants pour chaque domaine SIP :</span><span class="sxs-lookup"><span data-stu-id="81144-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="81144-111">un enregistrement DNS interne afin de prendre en charge les utilisateurs qui se connectent depuis le réseau de votre organisation ;</span><span class="sxs-lookup"><span data-stu-id="81144-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="81144-112">un enregistrement DNS externe, ou public, afin de prendre en charge les utilisateurs mobiles qui se connectent depuis Internet.</span><span class="sxs-lookup"><span data-stu-id="81144-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="81144-p102">L’URL de découverte automatique interne ne doit pas être adressable depuis l’extérieur de votre réseau. L’URL de découverte automatique externe ne doit pas être adressable depuis votre réseau. Toutefois, si cette condition ne peut pas être remplie pour l’URL externe, la fonctionnalité du client mobile ne devrait pas être affectée.</span><span class="sxs-lookup"><span data-stu-id="81144-p102">The internal automatic discovery URL should not be addressable from outside your network. The external automatic discovery URL should not be addressable from within your network. However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="81144-116">Les enregistrements DNS peuvent être des enregistrements CNAME ou des enregistrements A (hôte).</span><span class="sxs-lookup"><span data-stu-id="81144-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="81144-117">**Enregistrements DNS internes**</span><span class="sxs-lookup"><span data-stu-id="81144-117">**Internal DNS records**</span></span>

<span data-ttu-id="81144-118">Vous devez créer l’un des enregistrements DNS internes suivants :</span><span class="sxs-lookup"><span data-stu-id="81144-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81144-119">Type d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="81144-119">Record type</span></span></th>
<th><span data-ttu-id="81144-120">Nom d’hôte ou définition SRV</span><span class="sxs-lookup"><span data-stu-id="81144-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="81144-121">Résolu en</span><span class="sxs-lookup"><span data-stu-id="81144-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81144-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="81144-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="81144-123">lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="81144-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="81144-124">Nom de domaine complet (FQDN) des services Web internes pour votre pool Directeur, si vous en avez un, ou pour votre pool frontal si vous ne disposez pas d’un directeur</span><span class="sxs-lookup"><span data-stu-id="81144-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81144-125">A (hôte)</span><span class="sxs-lookup"><span data-stu-id="81144-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="81144-126">lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="81144-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="81144-127">Adresse IP interne des services Web (adresse IP virtuelle (VIP) si vous utilisez un programme d’équilibrage de la charge) de votre pool Directeur, si vous en avez un, ou de votre pool frontal si vous ne disposez pas d’un directeur</span><span class="sxs-lookup"><span data-stu-id="81144-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="81144-128">**Enregistrements DNS externes**</span><span class="sxs-lookup"><span data-stu-id="81144-128">**External DNS records**</span></span>

<span data-ttu-id="81144-129">Vous devez créer l’un des enregistrements DNS externes suivants :</span><span class="sxs-lookup"><span data-stu-id="81144-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81144-130">Type d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="81144-130">Record type</span></span></th>
<th><span data-ttu-id="81144-131">Nom d’hôte</span><span class="sxs-lookup"><span data-stu-id="81144-131">Host name</span></span></th>
<th><span data-ttu-id="81144-132">Résolu en</span><span class="sxs-lookup"><span data-stu-id="81144-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81144-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="81144-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="81144-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="81144-134">lyncdiscover.</span></span> <span data-ttu-id="81144-135">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="81144-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="81144-136">Nom de domaine complet externe des services Web pour votre pool Directeur, si vous en avez un, ou pour votre pool frontal si vous n’avez pas de directeur</span><span class="sxs-lookup"><span data-stu-id="81144-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81144-137">A (hôte)</span><span class="sxs-lookup"><span data-stu-id="81144-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="81144-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="81144-138">lyncdiscover.</span></span> <span data-ttu-id="81144-139">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="81144-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="81144-140">Adresse IP externe ou publique (adresse VIP si vous utilisez un programme d’équilibrage de la charge) du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="81144-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81144-141">SRV</span><span class="sxs-lookup"><span data-stu-id="81144-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="81144-142">_sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="81144-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="81144-143">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="81144-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="81144-144">Résout l’enregistrement d’hôte (A ou AAAA) pour le service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="81144-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81144-145">Pour prendre en charge le service de notifications et le service de notifications d’Apple, vous devez créer un enregistrement SRV pour chaque domaine SIP doté de clients Microsoft Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="81144-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="81144-146">Cette exigence s’applique uniquement aux clients mobiles Microsoft Lync sur des appareils mobiles Apple ou Microsoft.</span><span class="sxs-lookup"><span data-stu-id="81144-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="81144-147">Les appareils Android et Nokia Symbian n’utilisent pas de notification push.</span><span class="sxs-lookup"><span data-stu-id="81144-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="81144-148">Lyncdiscover, également appelé découverte automatique, le trafic passe par le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="81144-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="81144-149">L’enregistrement SRV pointe vers un enregistrement qui est résolu via le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="81144-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

