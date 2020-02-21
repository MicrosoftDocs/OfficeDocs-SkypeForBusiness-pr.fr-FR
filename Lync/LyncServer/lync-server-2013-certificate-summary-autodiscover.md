---
title: 'Lync Server 2013 : Résumé des certificats-découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7424d0c002e5b14335a6d0256fc72a3beff733cc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="2d5cb-102">Résumé des certificats-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d5cb-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d5cb-103">_**Dernière modification de la rubrique :** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="2d5cb-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="2d5cb-104">Le service de découverte automatique Lync Server 2013 s’exécute sur les serveurs de pools frontaux et de directeurs et, lorsqu’il est publié dans DNS, peut être utilisé par les clients Lync pour localiser les services de serveur et d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="2d5cb-105">Si vous effectuez une mise à niveau à partir de Lync Server 2010 et que vous n’avez pas déployé la mobilité, avant que les clients puissent utiliser la découverte automatique, vous devez modifier les listes des autres noms de sujet du certificat sur un directeur et un serveur frontal exécutant le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="2d5cb-106">En outre, il peut s’avérer nécessaire de modifier les listes des autres noms de sujet sur les certificats utilisés pour les règles de publication des services web externes sur les proxys inverses.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="2d5cb-107">La décision d’utiliser des listes d’autres noms de sujet sur les proxys inverses est basée sur la publication du service de découverte automatique sur le port 80 ou sur le port 443 :</span><span class="sxs-lookup"><span data-stu-id="2d5cb-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="2d5cb-108">**Publié sur le port 80**   aucune modification de certificat n’est requise si la requête initiale du service de découverte automatique a lieu sur le port 80.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="2d5cb-109">Cela est dû au fait que les appareils mobiles exécutant Lync accèdent au proxy inverse sur le port 80 de manière externe, puis sont transférés vers un directeur ou un serveur frontal sur le port 8080 en interne.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="2d5cb-110">Pour plus d’informations, reportez-vous à la section « processus de découverte automatique à l’aide du port 80 » [configuration technique requise pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="2d5cb-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="2d5cb-111">**Publié sur le port 443**   la liste autre nom du sujet sur les certificats utilisés par la règle de publication des services Web externes doit contenir un *lyncdiscover.\< entrée\> sipdomain* pour chaque domaine SIP au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2d5cb-112">Nous vous recommandons vivement d’utiliser le protocole HTTPs sur HTTP.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="2d5cb-113">HTTPs utilise des certificats pour chiffrer le trafic.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="2d5cb-114">HTTP ne fournit pas de chiffrement, et toutes les données envoyées seront en texte brut.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="2d5cb-115">La réémission de certificats à l’aide d’une autorité de certification interne est généralement un processus simple.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="2d5cb-116">Toutefois, pour les certificats publics utilisés sur la règle de publication du service Web, l’ajout de plusieurs entrées de l’autre nom du sujet peut devenir onéreux.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="2d5cb-117">Pour contourner ce problème, nous prenons en charge la connexion de découverte automatique initiale via le port 80, qui est ensuite redirigé vers le port 8080 sur le directeur ou le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d5cb-118">Si votre infrastructure Lync Server 2013 utilise des certificats internes émis par une autorité de certification interne et que vous envisagez de prendre en charge les appareils mobiles qui se connectent sans fil, la chaîne de certificats racine de l’autorité de certification interne doit être installée. sur les appareils mobiles ou vous devez passer à un certificat public sur votre infrastructure Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="2d5cb-119">Cette rubrique décrit les autres noms d’objet supplémentaires requis pour le directeur, le serveur frontal et le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="2d5cb-120">Seuls les autres noms de sujet (SAN) sont référencés.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="2d5cb-121">Reportez-vous aux sections de planification pour obtenir des instructions sur les autres entrées sur les certificats.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="2d5cb-122">Pour plus d’informations, reportez-vous à [la rubrique scénarios pour le directeur dans Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)et [scénarios pour le proxy inverse dans Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="2d5cb-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="2d5cb-123">Les tableaux suivants définissent les entrées SAN de découverte automatique pour le pool Directeur, le pool frontal et le proxy inverse :</span><span class="sxs-lookup"><span data-stu-id="2d5cb-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="2d5cb-124">Exigences relatives au certificat du pool directeur</span><span class="sxs-lookup"><span data-stu-id="2d5cb-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d5cb-125">Description</span><span class="sxs-lookup"><span data-stu-id="2d5cb-125">Description</span></span></th>
<th><span data-ttu-id="2d5cb-126">Entrée d’autre nom de sujet</span><span class="sxs-lookup"><span data-stu-id="2d5cb-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d5cb-127">URL du service de découverte automatique interne</span><span class="sxs-lookup"><span data-stu-id="2d5cb-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="2d5cb-128">SAN = lyncdiscoverinternal. &lt;nom de domaine interne&gt;</span><span class="sxs-lookup"><span data-stu-id="2d5cb-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d5cb-129">URL du service de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="2d5cb-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="2d5cb-130">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="2d5cb-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2d5cb-131">Vous affectez le certificat que vous venez de mettre à jour avec la nouvelle entrée SAN au certificat par défaut.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="2d5cb-132">Vous pouvez également utiliser le SAN = \*. &lt;sipdomain&gt;.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="2d5cb-133">Exigences relatives au certificat du pool frontal</span><span class="sxs-lookup"><span data-stu-id="2d5cb-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d5cb-134">Description</span><span class="sxs-lookup"><span data-stu-id="2d5cb-134">Description</span></span></th>
<th><span data-ttu-id="2d5cb-135">Entrée d’autre nom de sujet</span><span class="sxs-lookup"><span data-stu-id="2d5cb-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d5cb-136">URL du service de découverte automatique interne</span><span class="sxs-lookup"><span data-stu-id="2d5cb-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="2d5cb-137">SAN = lyncdiscoverinternal. &lt;nom de domaine interne&gt;</span><span class="sxs-lookup"><span data-stu-id="2d5cb-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d5cb-138">URL du service de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="2d5cb-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="2d5cb-139">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="2d5cb-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2d5cb-140">Vous affectez le certificat que vous venez de mettre à jour avec la nouvelle entrée SAN au certificat par défaut.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="2d5cb-141">Vous pouvez également utiliser le SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="2d5cb-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="2d5cb-142">Exigences relatives au certificat de proxy inverse (autorité de certification publique)</span><span class="sxs-lookup"><span data-stu-id="2d5cb-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d5cb-143">Description</span><span class="sxs-lookup"><span data-stu-id="2d5cb-143">Description</span></span></th>
<th><span data-ttu-id="2d5cb-144">Entrée d’autre nom de sujet</span><span class="sxs-lookup"><span data-stu-id="2d5cb-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d5cb-145">URL du service de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="2d5cb-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="2d5cb-146">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="2d5cb-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2d5cb-147">Vous affectez le certificat récemment mis à jour avec la nouvelle entrée SAN à l’écouteur SSL sur le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="2d5cb-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

