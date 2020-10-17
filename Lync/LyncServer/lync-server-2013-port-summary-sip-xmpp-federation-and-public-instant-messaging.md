---
title: Résumé des ports-SIP, Fédération XMPP et messagerie instantanée publique
description: Résumé des ports-SIP, Fédération XMPP et messagerie instantanée publique.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c58dbf7bdd56b4678d56f96a11332219bb40c17
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566354"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="dfedb-103">Résumé des ports-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfedb-103">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfedb-104">_**Dernière modification de la rubrique :** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="dfedb-104">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="dfedb-105">La configuration requise pour les ports, les protocoles et les pare-feu pour la Fédération avec Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server est similaire à celle du serveur Edge déployé.</span><span class="sxs-lookup"><span data-stu-id="dfedb-105">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="dfedb-106">Les clients initient la communication avec le service Edge d’accès via TLS/SIP/TCP 443.</span><span class="sxs-lookup"><span data-stu-id="dfedb-106">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="dfedb-107">Toutefois, les partenaires fédérés initieront des communications vers le service Edge d’accès via MTLS/SIP/TCP 5061.</span><span class="sxs-lookup"><span data-stu-id="dfedb-107">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="dfedb-108">Pour configurer votre pare-feu pour les ports et les protocoles nécessaires à la prise en charge de la connectivité de messagerie instantanée publique, notez d’abord que SIP/MTLS/TCP 5061 est bidirectionnel afin de tenir compte de la capacité des contacts dans le fournisseur de messagerie instantanée publique à contacter les clients Lync ou à contacter les contacts de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="dfedb-108">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="dfedb-109">Windows Live Messenger peut participer à des communications audio/vidéo avec des clients Lync.</span><span class="sxs-lookup"><span data-stu-id="dfedb-109">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="dfedb-110">Cela tient compte des ports de pare-feu et de la configuration de protocole très similaires dont vous disposez généralement sur le pare-feu pour prendre en charge les clients Lync en tant qu’utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="dfedb-110">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="dfedb-111">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="dfedb-111">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="dfedb-112">La Fédération avec Windows Live Messenger ne requiert pas de licences utilisateur/périphérique supplémentaires au-delà de la licence d’accès client (CAL) standard Lync.</span><span class="sxs-lookup"><span data-stu-id="dfedb-112">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="dfedb-113">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="dfedb-113">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="dfedb-114">Les contacts de la Fédération avec des clients Messenger se termineront officiellement le 15 mars 2013, à l’exception de la Chine continentale.</span><span class="sxs-lookup"><span data-stu-id="dfedb-114">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="dfedb-115">Skype devient le client de Fédération pour les utilisateurs fédérés qui utilisaient précédemment Messenger.</span><span class="sxs-lookup"><span data-stu-id="dfedb-115">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="dfedb-116">Les ports et protocoles définis pour le proxy XMPP (extensible Messaging and Presence Protocol) déployé sur le serveur Edge autorisent les communications du partenaire fédéré XMPP au serveur Edge et permettent également la communication entre votre serveur Edge et le partenaire fédéré XMPP.</span><span class="sxs-lookup"><span data-stu-id="dfedb-116">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="dfedb-117">Une règle est également définie sur le pare-feu orienté vers l’intérieur du serveur frontal ou du pool frontal vers le serveur Edge ou le pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="dfedb-117">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="dfedb-118">Résumé du pare-feu-Fédération SIP</span><span class="sxs-lookup"><span data-stu-id="dfedb-118">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfedb-119">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="dfedb-119">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dfedb-120">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="dfedb-120">Source IP address</span></span></th>
<th><span data-ttu-id="dfedb-121">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="dfedb-121">Destination IP address</span></span></th>
<th><span data-ttu-id="dfedb-122">Notes</span><span class="sxs-lookup"><span data-stu-id="dfedb-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfedb-123">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dfedb-123">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dfedb-124">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="dfedb-124">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dfedb-125">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="dfedb-125">Any</span></span></p></td>
<td><p><span data-ttu-id="dfedb-126">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="dfedb-126">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="dfedb-127">Résumé du pare-feu : connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="dfedb-127">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfedb-128">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="dfedb-128">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dfedb-129">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="dfedb-129">Source IP address</span></span></th>
<th><span data-ttu-id="dfedb-130">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="dfedb-130">Destination IP address</span></span></th>
<th><span data-ttu-id="dfedb-131">Notes</span><span class="sxs-lookup"><span data-stu-id="dfedb-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfedb-132">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dfedb-132">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dfedb-133">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="dfedb-133">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="dfedb-134">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="dfedb-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="dfedb-135">Pour la connectivité de messagerie instantanée publique et fédérée qui utilisent SIP.</span><span class="sxs-lookup"><span data-stu-id="dfedb-135">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfedb-136">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dfedb-136">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dfedb-137">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="dfedb-137">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="dfedb-138">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="dfedb-138">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="dfedb-139">Pour la connectivité de messagerie instantanée publique et fédérée qui utilisent SIP.</span><span class="sxs-lookup"><span data-stu-id="dfedb-139">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfedb-140">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dfedb-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dfedb-141">Clients</span><span class="sxs-lookup"><span data-stu-id="dfedb-141">Clients</span></span></p></td>
<td><p><span data-ttu-id="dfedb-142">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="dfedb-142">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="dfedb-143">Trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="dfedb-143">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfedb-144">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="dfedb-144">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="dfedb-145">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="dfedb-145">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="dfedb-146">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="dfedb-146">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="dfedb-147">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC est configurée.</span><span class="sxs-lookup"><span data-stu-id="dfedb-147">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfedb-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dfedb-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="dfedb-149">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="dfedb-149">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="dfedb-150">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="dfedb-150">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="dfedb-151">Obligatoire pour la connectivité PIC avec Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="dfedb-151">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfedb-152">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dfedb-152">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="dfedb-153">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="dfedb-153">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="dfedb-154">Interface d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="dfedb-154">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="dfedb-155">Obligatoire pour la connectivité PIC avec Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="dfedb-155">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="dfedb-156">Résumé du pare-feu-protocole XMPP (extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="dfedb-156">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfedb-157">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="dfedb-157">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dfedb-158">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="dfedb-158">Source (IP address)</span></span></th>
<th><span data-ttu-id="dfedb-159">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="dfedb-159">Destination (IP address)</span></span></th>
<th><span data-ttu-id="dfedb-160">Comments</span><span class="sxs-lookup"><span data-stu-id="dfedb-160">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfedb-161">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="dfedb-161">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="dfedb-162">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="dfedb-162">Any</span></span></p></td>
<td><p><span data-ttu-id="dfedb-163">Adresse IP de l’interface du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="dfedb-163">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="dfedb-164">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="dfedb-164">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="dfedb-165">Autorise la communication vers le proxy XMPP du serveur Edge à partir de partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="dfedb-165">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfedb-166">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="dfedb-166">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="dfedb-167">Adresse IP de l’interface du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="dfedb-167">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="dfedb-168">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="dfedb-168">Any</span></span></p></td>
<td><p><span data-ttu-id="dfedb-169">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="dfedb-169">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="dfedb-170">Autorise la communication du proxy XMPP serveur Edge aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="dfedb-170">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfedb-171">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="dfedb-171">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="dfedb-172">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="dfedb-172">Any</span></span></p></td>
<td><p><span data-ttu-id="dfedb-173">Adresse IP de l’interface du serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="dfedb-173">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="dfedb-174">Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool frontal vers le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="dfedb-174">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dfedb-175">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dfedb-175">See Also</span></span>


[<span data-ttu-id="dfedb-176">Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfedb-176">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="dfedb-177">Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfedb-177">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="dfedb-178">Gérer les partenaires fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfedb-178">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

