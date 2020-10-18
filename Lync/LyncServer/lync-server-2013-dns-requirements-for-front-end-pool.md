---
title: 'Lync Server 2013 : configuration DNS requise pour le pool frontal'
description: 'Lync Server 2013 : configuration DNS requise pour le pool frontal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfce90eccb8c8dff94d4122c96c4ca68ea9150f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574330"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="5c1eb-103">Configuration DNS requise pour le pool frontal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c1eb-103">DNS requirements for Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c1eb-104">_**Dernière modification de la rubrique :** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="5c1eb-104">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="5c1eb-105">Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="5c1eb-106">Vous devez configurer les enregistrements DNS (Domain Name System) requis avant de publier votre topologie dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-106">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="5c1eb-107">De plus, certains des noms de domaine complets utilisés dans la configuration d’un déploiement Lync Server 2013 sont logiques et non des noms de domaine complets de serveur physiques, de sorte que la configuration DNS supplémentaire est requise avant la publication.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-107">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5c1eb-108">Lync Server 2013 ne prend pas en charge les domaines à étiquette unique.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-108">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="5c1eb-109">Par exemple, une forêt comportant le domaine racine <STRONG>contoso.local</STRONG> est prise en charge alors que le domaine racine <STRONG>local</STRONG> ne l’est pas.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-109">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="5c1eb-110">Pour plus d’informations, consultez l’article 300684 de la base de connaissances Microsoft, « informations sur la configuration de Windows pour les domaines avec des noms DNS en une seule partie » à l’adresse <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-110">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5c1eb-111">Le nom que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-111">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="5c1eb-112">Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, pas un nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="5c1eb-112">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="5c1eb-113">Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-113">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="5c1eb-114"><STRONG>Utilisez uniquement des caractères standard</STRONG> (tels que a – z, a – z, 0 – 9 et des tirets) lorsque vous affectez des noms de domaine complets à vos serveurs exécutant Lync Server, des serveurs Edge et des pools.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-114"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="5c1eb-115">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-115">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="5c1eb-116">Les caractères non standard figurant dans un nom de domaine complet ne sont en général pas pris en charge par les serveurs DNS externes et les autorités de certification publiques (lorsque le nom de domaine complet doit être affecté au SN dans le certificat).</span><span class="sxs-lookup"><span data-stu-id="5c1eb-116">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="5c1eb-117">Avant de faire fonctionner la topologie une fois qu’elle a été déployée, vérifiez que les enregistrements Active Directory et DNS suivants sont créés (en fonction de vos besoins en matière de fonctionnalités spécifiques) :</span><span class="sxs-lookup"><span data-stu-id="5c1eb-117">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="5c1eb-118">Chaque rôle serveur qui existe dans la topologie est publié en tant qu’objet Active Directory (le fait de joindre l’ordinateur au domaine effectue cette opération).</span><span class="sxs-lookup"><span data-stu-id="5c1eb-118">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="5c1eb-119">Un enregistrement DNS A existe pour chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-119">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="5c1eb-120">Un enregistrement DNS SRV existe pour chaque domaine SIP si vous envisagez d’utiliser l’ouverture de session automatique pour les clients sous la forme d' \_ sipinternaltls \_ TCP. \<SIP domain\> .</span><span class="sxs-lookup"><span data-stu-id="5c1eb-120">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="5c1eb-121">Si vous utilisez la configuration manuelle pour les clients, cet enregistrement n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-121">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="5c1eb-122">Un enregistrement DNS A pour chaque URL simple configurée, dont il y a généralement quatre : réunion, numérotation, LWA et planificateur.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-122">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="5c1eb-123">De plus, il existe une URL simple d’administration qui est une URL spéciale pour accéder au panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-123">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="5c1eb-124">Le serveur exécutant SQL Server doit être joint au domaine et accessible par l’ordinateur à partir duquel le générateur de topologies est publié.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-124">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="5c1eb-125">Le tableau suivant indique les architectures de référence présentées dans la section Planification.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-125">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="5c1eb-126">Pour plus d’informations, reportez-vous à [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-126">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="5c1eb-127">Enregistrements DNS requis pour le pool frontal</span><span class="sxs-lookup"><span data-stu-id="5c1eb-127">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c1eb-128">Emplacement</span><span class="sxs-lookup"><span data-stu-id="5c1eb-128">Location</span></span></th>
<th><span data-ttu-id="5c1eb-129">Type</span><span class="sxs-lookup"><span data-stu-id="5c1eb-129">Type</span></span></th>
<th><span data-ttu-id="5c1eb-130">FQDN</span><span class="sxs-lookup"><span data-stu-id="5c1eb-130">FQDN</span></span></th>
<th><span data-ttu-id="5c1eb-131">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="5c1eb-131">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c1eb-132">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-132">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-133">A</span><span class="sxs-lookup"><span data-stu-id="5c1eb-133">A</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-134">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5c1eb-134">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-135">Pool01 (équilibrage de charge DNS).</span><span class="sxs-lookup"><span data-stu-id="5c1eb-135">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="5c1eb-136">Nécessite un enregistrement DNS A pour l’adresse IP de chaque serveur frontal dans le pool, mappé au nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-136">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c1eb-137">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-137">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-138">A</span><span class="sxs-lookup"><span data-stu-id="5c1eb-138">A</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-139">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5c1eb-139">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-140">Pool01 (adresse IP virtuelle (VIP) de l’équilibreur de la charge matérielle).</span><span class="sxs-lookup"><span data-stu-id="5c1eb-140">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c1eb-141">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-141">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-142">A</span><span class="sxs-lookup"><span data-stu-id="5c1eb-142">A</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-143">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5c1eb-143">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="5c1eb-144">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5c1eb-144">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="5c1eb-145">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5c1eb-145">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="5c1eb-146">…</span><span class="sxs-lookup"><span data-stu-id="5c1eb-146">…</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-147">Serveur frontal Pool01 (nœud 1).</span><span class="sxs-lookup"><span data-stu-id="5c1eb-147">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="5c1eb-148">Serveur frontal Pool01 (nœud 2).</span><span class="sxs-lookup"><span data-stu-id="5c1eb-148">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="5c1eb-149">Serveur frontal Pool01 (nœud 3).</span><span class="sxs-lookup"><span data-stu-id="5c1eb-149">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="5c1eb-150">…</span><span class="sxs-lookup"><span data-stu-id="5c1eb-150">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c1eb-151">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-151">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-152">A</span><span class="sxs-lookup"><span data-stu-id="5c1eb-152">A</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-153">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5c1eb-153">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-154">Serveur frontal Pool01 (nœud 2).</span><span class="sxs-lookup"><span data-stu-id="5c1eb-154">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c1eb-155">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-155">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-156">A</span><span class="sxs-lookup"><span data-stu-id="5c1eb-156">A</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-157">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5c1eb-157">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-158">Pool01 (VIP) pour le trafic web client à serveur.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-158">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c1eb-159">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-159">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-160">A</span><span class="sxs-lookup"><span data-stu-id="5c1eb-160">A</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-161">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5c1eb-161">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-162">Serveur principal Pool01 exécutant SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-162">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c1eb-163">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-163">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-164">A</span><span class="sxs-lookup"><span data-stu-id="5c1eb-164">A</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5c1eb-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-166">Requis pour Lync Phone Edition, ou ouverture de session automatique des clients sans enregistrements DNS SRV, et pour une correspondance de domaine stricte.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-166">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="5c1eb-167">Non requis dans tous les cas.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-167">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c1eb-168">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-168">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-169">A</span><span class="sxs-lookup"><span data-stu-id="5c1eb-169">A</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-170">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5c1eb-170">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-171">Suppose qu’il existe un second domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-171">Assumes a second SIP domain.</span></span> <span data-ttu-id="5c1eb-172">Obligatoire pour Lync Phone Edition, l’ouverture de session automatique des clients sans enregistrements DNS SRV et pour une correspondance de domaine stricte.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-172">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="5c1eb-173">Non requis dans tous les cas.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-173">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c1eb-174">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-174">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-175">A</span><span class="sxs-lookup"><span data-stu-id="5c1eb-175">A</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-176">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5c1eb-176">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-177">URL simple pour les conférences rendez-vous publiées en interne : le serveur frontal (ou directeur, s’il est installé) répond aux requêtes d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-177">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c1eb-178">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-178">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-179">A</span><span class="sxs-lookup"><span data-stu-id="5c1eb-179">A</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-180">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5c1eb-180">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-181">URL simple pour les conférences publiées en interne – le serveur frontal (ou directeur, s’il est installé) répond aux requêtes d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-181">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c1eb-182">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-182">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-183">A</span><span class="sxs-lookup"><span data-stu-id="5c1eb-183">A</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-184">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5c1eb-184">admin.contoso.com</span></span></p>
<p><span data-ttu-id="5c1eb-185">administration</span><span class="sxs-lookup"><span data-stu-id="5c1eb-185">admin</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-186">Enregistrement facultatif, URL simple pour le panneau de configuration Lync Server 2013 publié en interne (ou directeur, s’il est installé) répond aux requêtes d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-186">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="5c1eb-187">Seul le nom de l’hôte (pas de nom de domaine) est recommandé.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-187">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5c1eb-188">VIP = adresse IP virtuelle de l’équilibreur de la charge matérielle</span><span class="sxs-lookup"><span data-stu-id="5c1eb-188">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="5c1eb-189">Enregistrements DNS SRV pour le pool frontal</span><span class="sxs-lookup"><span data-stu-id="5c1eb-189">DNS SRV Records for the Front End pool</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c1eb-190">Emplacement</span><span class="sxs-lookup"><span data-stu-id="5c1eb-190">Location</span></span></th>
<th><span data-ttu-id="5c1eb-191">Type</span><span class="sxs-lookup"><span data-stu-id="5c1eb-191">Type</span></span></th>
<th><span data-ttu-id="5c1eb-192">FQDN</span><span class="sxs-lookup"><span data-stu-id="5c1eb-192">FQDN</span></span></th>
<th><span data-ttu-id="5c1eb-193">FQDN cible</span><span class="sxs-lookup"><span data-stu-id="5c1eb-193">Target FQDN</span></span></th>
<th><span data-ttu-id="5c1eb-194">Port</span><span class="sxs-lookup"><span data-stu-id="5c1eb-194">Port</span></span></th>
<th><span data-ttu-id="5c1eb-195">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="5c1eb-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c1eb-196">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-196">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-197">SRV</span><span class="sxs-lookup"><span data-stu-id="5c1eb-197">SRV</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-198">_sipinternaltls _sipinternaltls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="5c1eb-198">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-199">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5c1eb-199">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-200">5061</span><span class="sxs-lookup"><span data-stu-id="5c1eb-200">5061</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-201">Nécessaire pour que la configuration automatique des clients Lync 2013 fonctionne en interne.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-201">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c1eb-202">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-202">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-203">SRV</span><span class="sxs-lookup"><span data-stu-id="5c1eb-203">SRV</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-204">_sipinternaltls _sipinternaltls._tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="5c1eb-204">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-205">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5c1eb-205">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-206">5061</span><span class="sxs-lookup"><span data-stu-id="5c1eb-206">5061</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-207">Nécessaire pour que la configuration automatique des clients Lync 2013 fonctionne en interne.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-207">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c1eb-208">DNS interne</span><span class="sxs-lookup"><span data-stu-id="5c1eb-208">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-209">SRV</span><span class="sxs-lookup"><span data-stu-id="5c1eb-209">SRV</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-210">_ntp _ntp._udp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="5c1eb-210">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-211">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5c1eb-211">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-212">123</span><span class="sxs-lookup"><span data-stu-id="5c1eb-212">123</span></span></p></td>
<td><p><span data-ttu-id="5c1eb-213">Source NTP (Network Time Protocol) requise pour les appareils exécutant Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-213">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="5c1eb-214">En interne, cet enregistrement doit pointer vers le contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="5c1eb-214">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="5c1eb-215">Si le contrôleur de domaine n’est pas défini, l’enregistrement essaiera d’utiliser le serveur NTP time.windows.com</span><span class="sxs-lookup"><span data-stu-id="5c1eb-215">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

