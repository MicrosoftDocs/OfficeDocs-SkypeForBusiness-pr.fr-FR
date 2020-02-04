---
title: 'Lync Server 2013 : configuration requise pour DNS pour la connexion automatique au client'
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
ms.openlocfilehash: 6d033621382587367630d9119c2176e976cb2c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="d308c-102">Configuration DNS requise pour la connexion automatique au client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d308c-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d308c-103">_**Dernière modification de la rubrique :** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="d308c-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="d308c-104">Cette section décrit les enregistrements DNS (Domain Name System) nécessaires à la connexion automatique du client.</span><span class="sxs-lookup"><span data-stu-id="d308c-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="d308c-105">Lorsque vous déployez vos serveurs Standard Edition ou pools frontal, vous pouvez configurer vos clients de manière à utiliser la découverte automatique pour vous connecter au serveur Standard Edition Server ou au pool frontal approprié.</span><span class="sxs-lookup"><span data-stu-id="d308c-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="d308c-106">Si vous envisagez de nécessiter la connexion manuelle de vos clients à Lync Server 2013, vous pouvez ignorer cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="d308c-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="d308c-107">Pour prendre en charge la connexion automatique au client, vous devez :</span><span class="sxs-lookup"><span data-stu-id="d308c-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="d308c-108">Désigner un serveur ou un pool unique pour distribuer et authentifier les demandes de connexion au client.</span><span class="sxs-lookup"><span data-stu-id="d308c-108">Designate a single server or pool to distribute and authenticate client sign-in requests.</span></span> <span data-ttu-id="d308c-109">Il peut s’agir d’un serveur ou d’un pool de votre organisation qui héberge des utilisateurs ou d’un serveur dédié ou d’un pool dédié à cette fin qui n’héberge aucun utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d308c-109">This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users.</span></span> <span data-ttu-id="d308c-110">Pour une disponibilité élevée, nous vous recommandons de désigner un pool frontal pour cette fonction.</span><span class="sxs-lookup"><span data-stu-id="d308c-110">For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="d308c-111">Créer un enregistrement SRV DNS interne pour prendre en charge la connexion automatique du client pour ce serveur ou pool.</span><span class="sxs-lookup"><span data-stu-id="d308c-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d308c-112">Dans les exigences d’enregistrement suivantes, le domaine SIP fait référence à la partie hôte des URI SIP attribués aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d308c-112">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users.</span></span> <span data-ttu-id="d308c-113">Par exemple, si les URI SIP sont du type \* @contoso. com, contoso.com est le domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="d308c-113">For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain.</span></span> <span data-ttu-id="d308c-114">Le domaine SIP est souvent différent du domaine interne d’Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d308c-114">The SIP domain is often different from the internal Active Directory domain.</span></span> <span data-ttu-id="d308c-115">Une organisation peut également prendre en charge plusieurs domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="d308c-115">An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="d308c-116">Pour activer la configuration automatique pour vos clients, vous devez créer un enregistrement SRV DNS interne qui mappe l’un des enregistrements suivants au nom de domaine complet (FQDN) du pool frontal ou du serveur Standard Edition qui répartit les demandes de connexion provenant de Lync clients</span><span class="sxs-lookup"><span data-stu-id="d308c-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="d308c-117">\_sipinternaltls. \_TCP. \<Domain\> -pour les connexions TLS internes</span><span class="sxs-lookup"><span data-stu-id="d308c-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="d308c-118">Vous n’avez besoin de créer qu’un seul enregistrement SRV pour le pool frontal ou le serveur Standard Edition Server, ou la distribution de demandes de connexion.</span><span class="sxs-lookup"><span data-stu-id="d308c-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="d308c-119">Le tableau suivant montre quelques exemples d’enregistrements nécessaires pour l’entreprise fictive contoso, qui prend en charge les domaines SIP de contoso.com et retail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d308c-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="d308c-120">Exemple d’enregistrements DNS requis pour la connexion automatique du client avec plusieurs domaines SIP</span><span class="sxs-lookup"><span data-stu-id="d308c-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d308c-121">Nom de domaine complet du pool frontal utilisé pour distribuer les demandes de connexion</span><span class="sxs-lookup"><span data-stu-id="d308c-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="d308c-122">Domaine SIP</span><span class="sxs-lookup"><span data-stu-id="d308c-122">SIP domain</span></span></th>
<th><span data-ttu-id="d308c-123">Enregistrement DNS SRV</span><span class="sxs-lookup"><span data-stu-id="d308c-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d308c-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d308c-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d308c-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d308c-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d308c-126">Un enregistrement SRV pour le domaine _sipinternaltls. _tcp. contoso. com sur le port 5061 qui correspond à pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d308c-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d308c-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d308c-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d308c-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d308c-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d308c-129">Un enregistrement SRV pour le domaine _sipinternaltls. _tcp. Retail. contoso. com sur le port 5061 qui correspond à pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d308c-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d308c-130">Par défaut, les requêtes pour les enregistrements DNS respectent le strict rapprochement de nom de domaine entre le domaine figurant dans le nom d’utilisateur et l’enregistrement SRV.</span><span class="sxs-lookup"><span data-stu-id="d308c-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="d308c-131">Si vous préférez que les requêtes DNS du client utilisent plutôt une correspondance de suffixes, vous pouvez configurer la stratégie de groupe DisableStrictDNSNaming.</span><span class="sxs-lookup"><span data-stu-id="d308c-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="d308c-132">Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-planning-for-clients-and-devices.md">planification des clients et des appareils dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="d308c-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="d308c-133">Exemple de certificats et d’enregistrements DNS requis pour la connexion automatique au client</span><span class="sxs-lookup"><span data-stu-id="d308c-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="d308c-134">Cet exemple utilise les mêmes noms d’exemples dans le tableau précédent.</span><span class="sxs-lookup"><span data-stu-id="d308c-134">This example uses the same example names in the preceding table.</span></span> <span data-ttu-id="d308c-135">L’organisation contoso prend en charge les domaines SIP de contoso.com et retail.contoso.com, et tous les utilisateurs ont un URI SIP dans l’une des formes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d308c-135">The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="d308c-136">\<@retail\>utilisateur. contoso.com</span><span class="sxs-lookup"><span data-stu-id="d308c-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="d308c-137">\<@contoso\>utilisateur. com</span><span class="sxs-lookup"><span data-stu-id="d308c-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

