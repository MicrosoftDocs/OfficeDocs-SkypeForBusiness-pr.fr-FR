---
title: 'Lync Server 2013 : configuration DNS requise pour le pool frontal'
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
ms.openlocfilehash: d0ace2b05b506b5bbf73177282747a66d212b38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="62d55-102">Configuration DNS requise pour le pool frontal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62d55-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62d55-103">_**Dernière modification de la rubrique :** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="62d55-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="62d55-104">Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="62d55-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="62d55-105">Vous devez configurer les enregistrements DNS (Domain Name System) requis avant de publier votre topologie dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="62d55-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="62d55-106">De plus, certains des noms de domaine complets utilisés dans la configuration d’un déploiement Lync Server 2013 sont logiques et non des noms de domaine complets de serveur physiques, de sorte que la configuration DNS supplémentaire est requise avant la publication.</span><span class="sxs-lookup"><span data-stu-id="62d55-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="62d55-107">Lync Server 2013 ne prend pas en charge les domaines à étiquette unique.</span><span class="sxs-lookup"><span data-stu-id="62d55-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="62d55-108">Par exemple, une forêt comportant le domaine racine <STRONG>contoso.local</STRONG> est prise en charge alors que le domaine racine <STRONG>local</STRONG> ne l’est pas.</span><span class="sxs-lookup"><span data-stu-id="62d55-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="62d55-109">Pour plus d’informations, consultez l’article 300684 de la base de connaissances Microsoft, « informations sur la configuration de Windows pour les domaines avec des noms DNS en une seule partie » à l’adresse <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="62d55-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="62d55-110">Le nom que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="62d55-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="62d55-111">Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, pas un nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="62d55-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="62d55-112">Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts.</span><span class="sxs-lookup"><span data-stu-id="62d55-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="62d55-113"><STRONG>Utilisez uniquement des caractères standard</STRONG> (tels que a – z, a – z, 0 – 9 et des tirets) lorsque vous affectez des noms de domaine complets à vos serveurs exécutant Lync Server, des serveurs Edge et des pools.</span><span class="sxs-lookup"><span data-stu-id="62d55-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="62d55-114">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="62d55-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="62d55-115">Les caractères non standard figurant dans un nom de domaine complet ne sont en général pas pris en charge par les serveurs DNS externes et les autorités de certification publiques (lorsque le nom de domaine complet doit être affecté au SN dans le certificat).</span><span class="sxs-lookup"><span data-stu-id="62d55-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="62d55-116">Avant de faire fonctionner la topologie une fois qu’elle a été déployée, vérifiez que les enregistrements Active Directory et DNS suivants sont créés (en fonction de vos besoins en matière de fonctionnalités spécifiques) :</span><span class="sxs-lookup"><span data-stu-id="62d55-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="62d55-117">Chaque rôle serveur qui existe dans la topologie est publié en tant qu’objet Active Directory (le fait de joindre l’ordinateur au domaine effectue cette opération).</span><span class="sxs-lookup"><span data-stu-id="62d55-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="62d55-118">Un enregistrement DNS A existe pour chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="62d55-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="62d55-119">Un enregistrement DNS SRV existe pour chaque domaine SIP si vous envisagez d’utiliser l’ouverture de session automatique pour \_les\_clients sous la forme d’un TCP sipinternaltls. \<Domaine\>SIP.</span><span class="sxs-lookup"><span data-stu-id="62d55-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="62d55-120">Si vous utilisez la configuration manuelle pour les clients, cet enregistrement n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="62d55-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="62d55-121">Un enregistrement DNS A pour chaque URL simple configurée, dont il y a généralement quatre : réunion, numérotation, LWA et planificateur.</span><span class="sxs-lookup"><span data-stu-id="62d55-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="62d55-122">De plus, il existe une URL simple d’administration qui est une URL spéciale pour accéder au panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62d55-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="62d55-123">Le serveur exécutant SQL Server doit être joint au domaine et accessible par l’ordinateur à partir duquel le générateur de topologies est publié.</span><span class="sxs-lookup"><span data-stu-id="62d55-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="62d55-124">Le tableau suivant indique les architectures de référence présentées dans la section Planification.</span><span class="sxs-lookup"><span data-stu-id="62d55-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="62d55-125">Pour plus d’informations, reportez-vous à [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="62d55-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="62d55-126">Enregistrements DNS requis pour le pool frontal</span><span class="sxs-lookup"><span data-stu-id="62d55-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62d55-127">L’emplacement</span><span class="sxs-lookup"><span data-stu-id="62d55-127">Location</span></span></th>
<th><span data-ttu-id="62d55-128">Type</span><span class="sxs-lookup"><span data-stu-id="62d55-128">Type</span></span></th>
<th><span data-ttu-id="62d55-129">FQDN</span><span class="sxs-lookup"><span data-stu-id="62d55-129">FQDN</span></span></th>
<th><span data-ttu-id="62d55-130">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="62d55-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62d55-131">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-132">A</span><span class="sxs-lookup"><span data-stu-id="62d55-132">A</span></span></p></td>
<td><p><span data-ttu-id="62d55-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="62d55-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="62d55-134">Pool01 (équilibrage de charge DNS).</span><span class="sxs-lookup"><span data-stu-id="62d55-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="62d55-135">Nécessite un enregistrement DNS A pour l’adresse IP de chaque serveur frontal dans le pool, mappé au nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="62d55-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62d55-136">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-137">A</span><span class="sxs-lookup"><span data-stu-id="62d55-137">A</span></span></p></td>
<td><p><span data-ttu-id="62d55-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="62d55-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="62d55-139">Pool01 (adresse IP virtuelle (VIP) de l’équilibreur de la charge matérielle).</span><span class="sxs-lookup"><span data-stu-id="62d55-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62d55-140">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-141">A</span><span class="sxs-lookup"><span data-stu-id="62d55-141">A</span></span></p></td>
<td><p><span data-ttu-id="62d55-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="62d55-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="62d55-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="62d55-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="62d55-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="62d55-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="62d55-145">…</span><span class="sxs-lookup"><span data-stu-id="62d55-145">…</span></span></p></td>
<td><p><span data-ttu-id="62d55-146">Serveur frontal Pool01 (nœud 1).</span><span class="sxs-lookup"><span data-stu-id="62d55-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="62d55-147">Serveur frontal Pool01 (nœud 2).</span><span class="sxs-lookup"><span data-stu-id="62d55-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="62d55-148">Serveur frontal Pool01 (nœud 3).</span><span class="sxs-lookup"><span data-stu-id="62d55-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="62d55-149">…</span><span class="sxs-lookup"><span data-stu-id="62d55-149">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62d55-150">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-151">A</span><span class="sxs-lookup"><span data-stu-id="62d55-151">A</span></span></p></td>
<td><p><span data-ttu-id="62d55-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="62d55-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="62d55-153">Serveur frontal Pool01 (nœud 2).</span><span class="sxs-lookup"><span data-stu-id="62d55-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62d55-154">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-155">A</span><span class="sxs-lookup"><span data-stu-id="62d55-155">A</span></span></p></td>
<td><p><span data-ttu-id="62d55-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="62d55-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="62d55-157">Pool01 (VIP) pour le trafic web client à serveur.</span><span class="sxs-lookup"><span data-stu-id="62d55-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62d55-158">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-159">A</span><span class="sxs-lookup"><span data-stu-id="62d55-159">A</span></span></p></td>
<td><p><span data-ttu-id="62d55-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="62d55-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="62d55-161">Serveur principal Pool01 exécutant SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="62d55-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62d55-162">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-163">A</span><span class="sxs-lookup"><span data-stu-id="62d55-163">A</span></span></p></td>
<td><p><span data-ttu-id="62d55-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="62d55-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="62d55-165">Requis pour Lync Phone Edition, ou ouverture de session automatique des clients sans enregistrements DNS SRV, et pour une correspondance de domaine stricte.</span><span class="sxs-lookup"><span data-stu-id="62d55-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="62d55-166">Non requis dans tous les cas.</span><span class="sxs-lookup"><span data-stu-id="62d55-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62d55-167">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-168">A</span><span class="sxs-lookup"><span data-stu-id="62d55-168">A</span></span></p></td>
<td><p><span data-ttu-id="62d55-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="62d55-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="62d55-170">Suppose qu’il existe un second domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="62d55-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="62d55-171">Obligatoire pour Lync Phone Edition, l’ouverture de session automatique des clients sans enregistrements DNS SRV et pour une correspondance de domaine stricte.</span><span class="sxs-lookup"><span data-stu-id="62d55-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="62d55-172">Non requis dans tous les cas.</span><span class="sxs-lookup"><span data-stu-id="62d55-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62d55-173">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-174">A</span><span class="sxs-lookup"><span data-stu-id="62d55-174">A</span></span></p></td>
<td><p><span data-ttu-id="62d55-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="62d55-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="62d55-176">URL simple pour les conférences rendez-vous publiées en interne : le serveur frontal (ou directeur, s’il est installé) répond aux requêtes d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="62d55-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62d55-177">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-178">A</span><span class="sxs-lookup"><span data-stu-id="62d55-178">A</span></span></p></td>
<td><p><span data-ttu-id="62d55-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="62d55-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="62d55-180">URL simple pour les conférences publiées en interne – le serveur frontal (ou directeur, s’il est installé) répond aux requêtes d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="62d55-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62d55-181">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-182">A</span><span class="sxs-lookup"><span data-stu-id="62d55-182">A</span></span></p></td>
<td><p><span data-ttu-id="62d55-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="62d55-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="62d55-184">administration</span><span class="sxs-lookup"><span data-stu-id="62d55-184">admin</span></span></p></td>
<td><p><span data-ttu-id="62d55-185">Enregistrement facultatif, URL simple pour le panneau de configuration Lync Server 2013 publié en interne (ou directeur, s’il est installé) répond aux requêtes d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="62d55-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="62d55-186">Seul le nom de l’hôte (pas de nom de domaine) est recommandé.</span><span class="sxs-lookup"><span data-stu-id="62d55-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="62d55-187">VIP = adresse IP virtuelle de l’équilibreur de la charge matérielle</span><span class="sxs-lookup"><span data-stu-id="62d55-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="62d55-188">Enregistrements DNS SRV pour le pool frontal</span><span class="sxs-lookup"><span data-stu-id="62d55-188">DNS SRV Records for the Front End pool</span></span>


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
<th><span data-ttu-id="62d55-189">L’emplacement</span><span class="sxs-lookup"><span data-stu-id="62d55-189">Location</span></span></th>
<th><span data-ttu-id="62d55-190">Type</span><span class="sxs-lookup"><span data-stu-id="62d55-190">Type</span></span></th>
<th><span data-ttu-id="62d55-191">FQDN</span><span class="sxs-lookup"><span data-stu-id="62d55-191">FQDN</span></span></th>
<th><span data-ttu-id="62d55-192">FQDN cible</span><span class="sxs-lookup"><span data-stu-id="62d55-192">Target FQDN</span></span></th>
<th><span data-ttu-id="62d55-193">Port</span><span class="sxs-lookup"><span data-stu-id="62d55-193">Port</span></span></th>
<th><span data-ttu-id="62d55-194">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="62d55-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62d55-195">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-196">SRV</span><span class="sxs-lookup"><span data-stu-id="62d55-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="62d55-197">_sipinternaltls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="62d55-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="62d55-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="62d55-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="62d55-199">5061</span><span class="sxs-lookup"><span data-stu-id="62d55-199">5061</span></span></p></td>
<td><p><span data-ttu-id="62d55-200">Nécessaire pour que la configuration automatique des clients Lync 2013 fonctionne en interne.</span><span class="sxs-lookup"><span data-stu-id="62d55-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62d55-201">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-202">SRV</span><span class="sxs-lookup"><span data-stu-id="62d55-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="62d55-203">_sipinternaltls. _tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="62d55-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="62d55-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="62d55-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="62d55-205">5061</span><span class="sxs-lookup"><span data-stu-id="62d55-205">5061</span></span></p></td>
<td><p><span data-ttu-id="62d55-206">Nécessaire pour que la configuration automatique des clients Lync 2013 fonctionne en interne.</span><span class="sxs-lookup"><span data-stu-id="62d55-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62d55-207">DNS interne</span><span class="sxs-lookup"><span data-stu-id="62d55-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="62d55-208">SRV</span><span class="sxs-lookup"><span data-stu-id="62d55-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="62d55-209">_ntp. _udp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="62d55-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="62d55-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="62d55-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="62d55-211">123</span><span class="sxs-lookup"><span data-stu-id="62d55-211">123</span></span></p></td>
<td><p><span data-ttu-id="62d55-212">Source NTP (Network Time Protocol) requise pour les appareils exécutant Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="62d55-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="62d55-213">En interne, cet enregistrement doit pointer vers le contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="62d55-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="62d55-214">Si le contrôleur de domaine n’est pas défini, l’enregistrement essaiera d’utiliser le serveur NTP time.windows.com</span><span class="sxs-lookup"><span data-stu-id="62d55-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

