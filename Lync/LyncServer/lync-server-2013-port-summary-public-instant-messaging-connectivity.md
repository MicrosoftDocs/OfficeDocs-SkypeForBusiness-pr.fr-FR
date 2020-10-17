---
title: 'Lync Server 2013 : Résumé des ports-connectivité de messagerie instantanée publique'
description: 'Lync Server 2013 : Résumé des ports-connectivité de messagerie instantanée publique.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4137b5f92e043dc15dc9aa1f0b9593b4d9f7c2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543060"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="b1f5a-103">Résumé des ports-connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1f5a-103">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1f5a-104">_**Dernière modification de la rubrique :** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="b1f5a-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="b1f5a-105">Pour configurer votre pare-feu pour les ports et les protocoles nécessaires à la prise en charge de la connectivité de messagerie instantanée publique, notez d’abord que SIP/MTLS/TCP 5061 est bidirectionnel afin de tenir compte de la capacité des contacts dans le fournisseur de messagerie instantanée publique à contacter les clients Lync ou à contacter les contacts de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-105">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="b1f5a-106">Windows Live Messenger peut participer à des communications audio/vidéo avec des clients Lync.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-106">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="b1f5a-107">Cela tient compte des ports de pare-feu et de la configuration de protocole très similaires dont vous disposez généralement sur le pare-feu pour prendre en charge les clients Lync en tant qu’utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-107">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b1f5a-108">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-108">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="b1f5a-109">La Fédération avec Windows Live Messenger ne requiert pas de licences utilisateur/périphérique supplémentaires au-delà de la licence d’accès client (CAL) standard Lync.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-109">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="b1f5a-110">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-110">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="b1f5a-111">Les contacts de la Fédération avec des clients Messenger se termineront officiellement le 15 mars 2013, à l’exception de la Chine continentale.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-111">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="b1f5a-112">Skype devient le client de Fédération pour les utilisateurs fédérés qui utilisaient précédemment Messenger.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-112">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b1f5a-113">Résumé du pare-feu : connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="b1f5a-113">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1f5a-114">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="b1f5a-114">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b1f5a-115">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="b1f5a-115">Source IP address</span></span></th>
<th><span data-ttu-id="b1f5a-116">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="b1f5a-116">Destination IP address</span></span></th>
<th><span data-ttu-id="b1f5a-117">Notes</span><span class="sxs-lookup"><span data-stu-id="b1f5a-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1f5a-118">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b1f5a-118">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-119">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="b1f5a-119">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-120">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b1f5a-120">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-121">Pour la connectivité de messagerie instantanée publique et fédérée qui utilisent SIP.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-121">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1f5a-122">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b1f5a-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-123">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b1f5a-123">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-124">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="b1f5a-124">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-125">Pour la connectivité de messagerie instantanée publique et fédérée qui utilisent SIP.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-125">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1f5a-126">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b1f5a-126">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-127">Clients</span><span class="sxs-lookup"><span data-stu-id="b1f5a-127">Clients</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-128">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b1f5a-128">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-129">Trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-129">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1f5a-130">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="b1f5a-130">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-131">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b1f5a-131">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-132">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b1f5a-132">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-133">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC est configurée.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-133">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1f5a-134">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b1f5a-134">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-135">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b1f5a-135">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-136">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b1f5a-136">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-137">Obligatoire pour la connectivité PIC avec Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-137">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1f5a-138">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b1f5a-138">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-139">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b1f5a-139">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-140">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b1f5a-140">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="b1f5a-141">Obligatoire pour la connectivité PIC avec Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="b1f5a-141">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1f5a-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1f5a-142">See Also</span></span>


[<span data-ttu-id="b1f5a-143">Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1f5a-143">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="b1f5a-144">Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1f5a-144">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

