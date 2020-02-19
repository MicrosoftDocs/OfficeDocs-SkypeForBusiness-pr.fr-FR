---
title: 'Lync Server 2013 : exigences en matière de certificats pour la mobilité'
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
ms.openlocfilehash: 5c3bf95f87fa663331f05861f91cd7f7f19a2728
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="c82c8-102">Exigences relatives aux certificats pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c82c8-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c82c8-103">_**Dernière modification de la rubrique :** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="c82c8-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="c82c8-104">Si vous déployez la fonctionnalité de mobilité et prenez en charge la découverte automatique pour les clients mobiles, vous devez inclure certaines entrée d’autres noms de sujet sur les certificats de manière prendre en charge les connexions sécurisées établies à partir de clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="c82c8-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="c82c8-105">Vous devez inclure des entrées d’autres noms de sujet pour la découverte automatique sur les certificats suivants :</span><span class="sxs-lookup"><span data-stu-id="c82c8-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="c82c8-106">pool directeur</span><span class="sxs-lookup"><span data-stu-id="c82c8-106">Director pool</span></span>

  - <span data-ttu-id="c82c8-107">pool frontal</span><span class="sxs-lookup"><span data-stu-id="c82c8-107">Front End pool</span></span>

  - <span data-ttu-id="c82c8-108">Proxy inverse</span><span class="sxs-lookup"><span data-stu-id="c82c8-108">Reverse proxy</span></span>

<span data-ttu-id="c82c8-109">Cette section décrit les entrées d’autres noms de sujet requises sur vos certificats pour la découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="c82c8-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c82c8-110">La réémission de certificats à l’aide d’une autorité de certification interne est généralement un processus simple, mais l’ajout de plusieurs entrées d’autres noms de sujet à des certificats publics utilisés par le proxy inverse peut être une opération coûteuse.</span><span class="sxs-lookup"><span data-stu-id="c82c8-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="c82c8-111">Si vous avez de nombreux domaines SIP, ce qui rend l’ajout d’autres noms de sujet très coûteux, vous pouvez configurer le proxy inverse de façon à utiliser le protocole HTTP pour la demande initiale du service de découverte automatique, plutôt que le protocole HTTPS (configuration par défaut).</span><span class="sxs-lookup"><span data-stu-id="c82c8-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="c82c8-112">Pour plus d’informations, voir <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical Requirements for Mobility in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c82c8-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="c82c8-113">Exigences relatives au certificat du pool directeur</span><span class="sxs-lookup"><span data-stu-id="c82c8-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c82c8-114">Description</span><span class="sxs-lookup"><span data-stu-id="c82c8-114">Description</span></span></th>
<th><span data-ttu-id="c82c8-115">Entrée d’autre nom de sujet</span><span class="sxs-lookup"><span data-stu-id="c82c8-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c82c8-116">URL du service de découverte automatique interne</span><span class="sxs-lookup"><span data-stu-id="c82c8-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="c82c8-117">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c82c8-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c82c8-118">URL du service de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="c82c8-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="c82c8-119">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c82c8-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c82c8-120">Vous pouvez également utiliser le SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c82c8-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="c82c8-121">Exigences relatives au certificat du pool frontal</span><span class="sxs-lookup"><span data-stu-id="c82c8-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c82c8-122">Description</span><span class="sxs-lookup"><span data-stu-id="c82c8-122">Description</span></span></th>
<th><span data-ttu-id="c82c8-123">Entrée d’autre nom de sujet</span><span class="sxs-lookup"><span data-stu-id="c82c8-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c82c8-124">URL du service de découverte automatique interne</span><span class="sxs-lookup"><span data-stu-id="c82c8-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="c82c8-125">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c82c8-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c82c8-126">URL du service de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="c82c8-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="c82c8-127">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c82c8-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c82c8-128">Vous pouvez également utiliser le SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c82c8-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="c82c8-129">Exigences relatives au certificat de proxy inverse (autorité de certification publique)</span><span class="sxs-lookup"><span data-stu-id="c82c8-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c82c8-130">Description</span><span class="sxs-lookup"><span data-stu-id="c82c8-130">Description</span></span></th>
<th><span data-ttu-id="c82c8-131">Entrée d’autre nom de sujet</span><span class="sxs-lookup"><span data-stu-id="c82c8-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c82c8-132">URL du service de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="c82c8-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="c82c8-133">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c82c8-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c82c8-134">Vous affecté cet autre nom d’objet (SAN) au certificat assigné à l’écouteur SSL sur le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="c82c8-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c82c8-135">Votre écouteur de proxy inverse aura des noms d’objet alternatifs pour vos URL de services Web externes (par exemple, SAN = lyncwebextpool01. contoso. com et dirwebexternal.contoso.com si vous avez déployé le directeur facultatif).</span><span class="sxs-lookup"><span data-stu-id="c82c8-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

