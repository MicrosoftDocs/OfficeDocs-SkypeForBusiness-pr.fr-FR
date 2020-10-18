---
title: 'Lync Server 2013 : configuration DNS requise pour la connexion automatique des clients'
description: 'Lync Server 2013 : configuration DNS requise pour la connexion automatique du client.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2247c955e0a563a22fb5d0ec20735291a836cdfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574370"
---
# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="ffadd-103">Configuration DNS requise pour la connexion automatique des clients dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffadd-103">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffadd-104">_**Dernière modification de la rubrique :** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="ffadd-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="ffadd-105">Cette section décrit les enregistrements DNS (Domain Name System) nécessaires à la connexion automatique des clients.</span><span class="sxs-lookup"><span data-stu-id="ffadd-105">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="ffadd-106">Quand vous déployez vos serveurs Standard Edition ou pools frontaux, vous pouvez configurer vos clients pour qu’ils utilisent la détection automatique pour se connecter au serveur Standard Edition ou pool frontal approprié.</span><span class="sxs-lookup"><span data-stu-id="ffadd-106">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="ffadd-107">Si vous envisagez de demander à vos clients de se connecter manuellement à Lync Server 2013, vous pouvez ignorer cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ffadd-107">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="ffadd-108">Pour prendre en charge la connexion automatique des clients, vous devez :</span><span class="sxs-lookup"><span data-stu-id="ffadd-108">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="ffadd-109">Désignez un seul serveur ou pool pour distribuer et authentifier les demandes de connexion client.</span><span class="sxs-lookup"><span data-stu-id="ffadd-109">Designate a single server or pool to distribute and authenticate client sign-in requests.</span></span> <span data-ttu-id="ffadd-110">Il peut s’agir d’un serveur ou d’un pool existant de votre organisation qui héberge des utilisateurs, ou vous pouvez désigner un serveur ou un pool dédié à cette fin qui n’héberge aucun utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ffadd-110">This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users.</span></span> <span data-ttu-id="ffadd-111">Pour la haute disponibilité, nous vous recommandons de désigner un pool frontal pour cette fonction.</span><span class="sxs-lookup"><span data-stu-id="ffadd-111">For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="ffadd-112">Créez un enregistrement DNS SRV interne pour prendre en charge la connexion automatique des clients pour ce serveur ou ce pool.</span><span class="sxs-lookup"><span data-stu-id="ffadd-112">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ffadd-113">Dans les conditions d’enregistrement suivantes, le domaine SIP fait référence à la partie hôte des URI SIP attribuées aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ffadd-113">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users.</span></span> <span data-ttu-id="ffadd-114">Par exemple, si les URI SIP ont la forme \* @contoso. com, contoso.com est le domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="ffadd-114">For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain.</span></span> <span data-ttu-id="ffadd-115">Le domaine SIP est souvent différent du domaine Active Directory interne.</span><span class="sxs-lookup"><span data-stu-id="ffadd-115">The SIP domain is often different from the internal Active Directory domain.</span></span> <span data-ttu-id="ffadd-116">Une organisation peut également prendre en charge plusieurs domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="ffadd-116">An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="ffadd-117">Pour activer la configuration automatique pour vos clients, vous devez créer un enregistrement DNS SRV interne qui mappe l’un des enregistrements suivants au nom de domaine complet (FQDN) du pool frontal ou du serveur Standard Edition qui distribue les demandes de connexion à partir de clients Lync :</span><span class="sxs-lookup"><span data-stu-id="ffadd-117">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="ffadd-118">\_sipinternaltls. \_ TCP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="ffadd-118">\_sipinternaltls.\_tcp.\<domain\></span></span> <span data-ttu-id="ffadd-119">-pour les connexions TLS internes</span><span class="sxs-lookup"><span data-stu-id="ffadd-119">- for internal TLS connections</span></span>

<span data-ttu-id="ffadd-120">Il vous suffit de créer un seul enregistrement SRV pour le pool frontal ou le serveur Standard Edition, ou de distribuer des demandes de connexion.</span><span class="sxs-lookup"><span data-stu-id="ffadd-120">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="ffadd-121">Le tableau suivant présente des exemples d’enregistrements requis pour la société fictive contoso, qui prend en charge les domaines SIP de contoso.com et retail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ffadd-121">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="ffadd-122">Exemple d’enregistrements DNS requis pour la connexion automatique des clients avec plusieurs domaines SIP</span><span class="sxs-lookup"><span data-stu-id="ffadd-122">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffadd-123">Nom de domaine complet du pool frontal utilisé pour distribuer les demandes de connexion</span><span class="sxs-lookup"><span data-stu-id="ffadd-123">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="ffadd-124">Domaine SIP</span><span class="sxs-lookup"><span data-stu-id="ffadd-124">SIP domain</span></span></th>
<th><span data-ttu-id="ffadd-125">Enregistrement DNS SRV</span><span class="sxs-lookup"><span data-stu-id="ffadd-125">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffadd-126">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ffadd-126">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ffadd-127">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ffadd-127">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ffadd-128">Un enregistrement SRV pour le domaine _sipinternaltls. _ TCP. contoso. com sur le port 5061 qui mappe sur pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ffadd-128">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffadd-129">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ffadd-129">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ffadd-130">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ffadd-130">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ffadd-131">Un enregistrement SRV pour le domaine _sipinternaltls. _ TCP. Retail. contoso. com sur le port 5061 qui mappe sur pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ffadd-131">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ffadd-132">Par défaut, les requêtes pour les enregistrements DNS respectent une correspondance de nom de domaine stricte entre le domaine dans le nom d’utilisateur et l’enregistrement SRV.</span><span class="sxs-lookup"><span data-stu-id="ffadd-132">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="ffadd-133">Si vous préférez que les requêtes DNS clientes utilisent la correspondance de suffixe, vous pouvez configurer la stratégie de groupe DisableStrictDNSNaming.</span><span class="sxs-lookup"><span data-stu-id="ffadd-133">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="ffadd-134">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="ffadd-134">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="ffadd-135">Exemple de certificats et d’enregistrements DNS requis pour les Sign-In client automatiques</span><span class="sxs-lookup"><span data-stu-id="ffadd-135">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="ffadd-136">Cet exemple utilise les mêmes exemples de noms dans le tableau précédent.</span><span class="sxs-lookup"><span data-stu-id="ffadd-136">This example uses the same example names in the preceding table.</span></span> <span data-ttu-id="ffadd-137">L’organisation contoso prend en charge les domaines SIP de contoso.com et retail.contoso.com, et tous ses utilisateurs ont un URI SIP dans l’un des formats suivants :</span><span class="sxs-lookup"><span data-stu-id="ffadd-137">The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="ffadd-138">\<user\>@retail. contoso.com</span><span class="sxs-lookup"><span data-stu-id="ffadd-138">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="ffadd-139">\<user\>@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ffadd-139">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

