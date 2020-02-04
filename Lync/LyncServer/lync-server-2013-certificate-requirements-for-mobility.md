---
title: 'Lync Server 2013 : Exigences relatives aux certificats pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 680eaf205959b67d8fef93ff56d379ae8cd293bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="10584-102">Exigences relatives aux certificats pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10584-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10584-103">_**Dernière modification de la rubrique :** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="10584-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="10584-104">Si vous déployez la fonctionnalité de mobilité et que vous prenez en charge la découverte automatique pour les clients mobiles, vous devez inclure certaines entrées de nom alternatif de sujet sur les certificats pour la prise en charge de connexions sécurisées à partir des clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="10584-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="10584-105">Vous devez inclure les autres entrées de nom de l’objet pour la découverte automatique sur les certificats suivants :</span><span class="sxs-lookup"><span data-stu-id="10584-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="10584-106">pool de directeurs</span><span class="sxs-lookup"><span data-stu-id="10584-106">Director pool</span></span>

  - <span data-ttu-id="10584-107">pool de serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="10584-107">Front End pool</span></span>

  - <span data-ttu-id="10584-108">Proxy inverse</span><span class="sxs-lookup"><span data-stu-id="10584-108">Reverse proxy</span></span>

<span data-ttu-id="10584-109">Cette section décrit les entrées de nom alternatif requises sur vos certificats pour une découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="10584-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="10584-110">La réémission de certificats à l’aide d’une autorité de certification interne correspond généralement à un processus simple, mais l’ajout de plusieurs entrées de nom de remplacement de sujet à des certificats publics utilisés par le proxy inverse peut être coûteux.</span><span class="sxs-lookup"><span data-stu-id="10584-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="10584-111">Si vous avez de nombreux domaines SIP, le fait d’ajouter des noms de substitution d’objet très coûteux, vous pouvez configurer le proxy inverse pour qu’il utilise HTTP pour la demande de service de découverte automatique initiale au lieu d’utiliser HTTPs (configuration par défaut).</span><span class="sxs-lookup"><span data-stu-id="10584-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="10584-112">Pour plus d’informations, voir <A href="lync-server-2013-technical-requirements-for-mobility.md">Configuration requise pour la mobilité dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="10584-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="10584-113">Conditions requises pour le certificat de pool de réalisateur</span><span class="sxs-lookup"><span data-stu-id="10584-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10584-114">Description</span><span class="sxs-lookup"><span data-stu-id="10584-114">Description</span></span></th>
<th><span data-ttu-id="10584-115">Entrée de l’autre nom de l’objet</span><span class="sxs-lookup"><span data-stu-id="10584-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10584-116">URL du service de découverte automatique interne</span><span class="sxs-lookup"><span data-stu-id="10584-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="10584-117">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="10584-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10584-118">URL du service de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="10584-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="10584-119">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="10584-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="10584-120">Vous pouvez également utiliser le SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="10584-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="10584-121">Conditions requises pour le certificat de pool frontal</span><span class="sxs-lookup"><span data-stu-id="10584-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10584-122">Description</span><span class="sxs-lookup"><span data-stu-id="10584-122">Description</span></span></th>
<th><span data-ttu-id="10584-123">Entrée de l’autre nom de l’objet</span><span class="sxs-lookup"><span data-stu-id="10584-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10584-124">URL du service de découverte automatique interne</span><span class="sxs-lookup"><span data-stu-id="10584-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="10584-125">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="10584-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10584-126">URL du service de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="10584-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="10584-127">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="10584-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="10584-128">Vous pouvez également utiliser le SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="10584-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="10584-129">Conditions requises pour les certificats de proxy inverse (AC publique)</span><span class="sxs-lookup"><span data-stu-id="10584-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10584-130">Description</span><span class="sxs-lookup"><span data-stu-id="10584-130">Description</span></span></th>
<th><span data-ttu-id="10584-131">Entrée de l’autre nom de l’objet</span><span class="sxs-lookup"><span data-stu-id="10584-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10584-132">URL du service de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="10584-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="10584-133">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="10584-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="10584-134">Vous attribuez ce SAN au certificat attribué à l’écouteur SSL sur le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="10584-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="10584-135">Votre écouteur de proxy inverse aura des noms de remplacement pour vos URL de services Web externes (par exemple, SAN = lyncwebextpool01. contoso. com et dirwebexternal.contoso.com si vous avez déployé le réalisateur facultatif).</span><span class="sxs-lookup"><span data-stu-id="10584-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

