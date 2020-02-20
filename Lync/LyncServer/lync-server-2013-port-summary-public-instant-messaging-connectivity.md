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
ms.openlocfilehash: 5f2d9b36e3a78b70dff97fabb08784dbbef9df9b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="517b0-102">Résumé des ports-connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="517b0-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="517b0-103">_**Dernière modification de la rubrique :** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="517b0-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="517b0-104">Pour configurer votre pare-feu pour les ports et les protocoles nécessaires à la prise en charge de la connectivité de messagerie instantanée publique, notez d’abord que SIP/MTLS/TCP 5061 est bidirectionnel afin de tenir compte de la capacité des contacts dans le fournisseur de messagerie instantanée publique à contacter les clients Lync ou à contacter les contacts de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="517b0-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="517b0-105">Windows Live Messenger peut participer à des communications audio/vidéo avec des clients Lync.</span><span class="sxs-lookup"><span data-stu-id="517b0-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="517b0-106">Cela tient compte des ports de pare-feu et de la configuration de protocole très similaires dont vous disposez généralement sur le pare-feu pour prendre en charge les clients Lync en tant qu’utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="517b0-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="517b0-107">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="517b0-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="517b0-108">La Fédération avec Windows Live Messenger ne requiert pas de licences utilisateur/périphérique supplémentaires au-delà de la licence d’accès client (CAL) standard Lync.</span><span class="sxs-lookup"><span data-stu-id="517b0-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="517b0-109">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="517b0-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="517b0-110">Les contacts de la Fédération avec des clients Messenger se termineront officiellement le 15 mars 2013, à l’exception de la Chine continentale.</span><span class="sxs-lookup"><span data-stu-id="517b0-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="517b0-111">Skype devient le client de Fédération pour les utilisateurs fédérés qui utilisaient précédemment Messenger.</span><span class="sxs-lookup"><span data-stu-id="517b0-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="517b0-112">Résumé du pare-feu : connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="517b0-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="517b0-113">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="517b0-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="517b0-114">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="517b0-114">Source IP address</span></span></th>
<th><span data-ttu-id="517b0-115">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="517b0-115">Destination IP address</span></span></th>
<th><span data-ttu-id="517b0-116">Notes</span><span class="sxs-lookup"><span data-stu-id="517b0-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="517b0-117">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="517b0-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="517b0-118">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="517b0-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="517b0-119">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="517b0-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="517b0-120">Pour la connectivité de messagerie instantanée publique et fédérée qui utilisent SIP.</span><span class="sxs-lookup"><span data-stu-id="517b0-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="517b0-121">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="517b0-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="517b0-122">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="517b0-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="517b0-123">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="517b0-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="517b0-124">Pour la connectivité de messagerie instantanée publique et fédérée qui utilisent SIP.</span><span class="sxs-lookup"><span data-stu-id="517b0-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="517b0-125">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="517b0-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="517b0-126">Clients</span><span class="sxs-lookup"><span data-stu-id="517b0-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="517b0-127">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="517b0-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="517b0-128">Trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="517b0-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="517b0-129">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="517b0-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="517b0-130">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="517b0-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="517b0-131">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="517b0-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="517b0-132">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC est configurée.</span><span class="sxs-lookup"><span data-stu-id="517b0-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="517b0-133">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="517b0-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="517b0-134">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="517b0-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="517b0-135">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="517b0-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="517b0-136">Obligatoire pour la connectivité PIC avec Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="517b0-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="517b0-137">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="517b0-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="517b0-138">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="517b0-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="517b0-139">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="517b0-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="517b0-140">Obligatoire pour la connectivité PIC avec Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="517b0-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="517b0-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="517b0-141">See Also</span></span>


[<span data-ttu-id="517b0-142">Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="517b0-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="517b0-143">Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="517b0-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

