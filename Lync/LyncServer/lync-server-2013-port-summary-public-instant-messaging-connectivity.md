---
title: 'Lync Server 2013 : Résumé des ports-connectivité de messagerie instantanée publique'
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
ms.openlocfilehash: 16430849221631d9b540f5ee51b0a07758a38b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="46214-102">Résumé de port-connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46214-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46214-103">_**Dernière modification de la rubrique :** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="46214-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="46214-104">Pour configurer votre pare-feu pour les ports et les protocoles nécessaires à la prise en charge de la connectivité de messagerie instantanée publique, notez d’abord que le protocole SIP/MTLS/TCP 5061 est bidirectionnel afin de tenir compte de la capacité des contacts du fournisseur de messagerie instantanée publique à contacter les clients Lync ou à communiquer avec des contacts de messagerie instantanée publics.</span><span class="sxs-lookup"><span data-stu-id="46214-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="46214-105">Windows Live Messenger peut participer aux communications audio/vidéo avec les clients Lync.</span><span class="sxs-lookup"><span data-stu-id="46214-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="46214-106">Il s’agit des comptes pour le pare-feu et la configuration de protocole très similaires dont vous disposez généralement sur le pare-feu pour la prise en charge des clients Lync en tant qu’utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="46214-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="46214-107">Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="46214-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="46214-108">La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisation/appareil supplémentaire au-delà de la licence d’accès client standard Lync.</span><span class="sxs-lookup"><span data-stu-id="46214-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="46214-109">Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</span><span class="sxs-lookup"><span data-stu-id="46214-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="46214-110">Les contacts de la Fédération avec le client Messenger se terminent officiellement le 15 mars 2013, à l’exception de la Chine continentale.</span><span class="sxs-lookup"><span data-stu-id="46214-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="46214-111">Skype deviendra le client de Fédération pour les utilisateurs fédérés qui utilisaient déjà Messenger.</span><span class="sxs-lookup"><span data-stu-id="46214-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="46214-112">Résumé du pare-feu-connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="46214-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46214-113">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="46214-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="46214-114">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="46214-114">Source IP address</span></span></th>
<th><span data-ttu-id="46214-115">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="46214-115">Destination IP address</span></span></th>
<th><span data-ttu-id="46214-116">Remarques</span><span class="sxs-lookup"><span data-stu-id="46214-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46214-117">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="46214-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46214-118">Partenaires de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="46214-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="46214-119">Interface d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="46214-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="46214-120">Pour la connectivité de messagerie instantanée fédérée et publique qui utilise SIP.</span><span class="sxs-lookup"><span data-stu-id="46214-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46214-121">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="46214-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46214-122">Interface d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="46214-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="46214-123">Partenaires de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="46214-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="46214-124">Pour la connectivité de messagerie instantanée fédérée et publique qui utilise SIP.</span><span class="sxs-lookup"><span data-stu-id="46214-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46214-125">/TCP/443 d’accès/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="46214-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46214-126">Clients</span><span class="sxs-lookup"><span data-stu-id="46214-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="46214-127">Interface d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="46214-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="46214-128">Trafic SIP client vers serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="46214-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46214-129">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="46214-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="46214-130">Interface d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="46214-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="46214-131">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="46214-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="46214-132">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC (Public IM Connectivity) est configurée.</span><span class="sxs-lookup"><span data-stu-id="46214-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46214-133">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="46214-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="46214-134">Interface d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="46214-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="46214-135">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="46214-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="46214-136">Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="46214-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46214-137">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="46214-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="46214-138">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="46214-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="46214-139">Interface d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="46214-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="46214-140">Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="46214-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46214-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46214-141">See Also</span></span>


[<span data-ttu-id="46214-142">Scénarios d’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46214-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="46214-143">Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46214-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

