---
title: Résumé des certificats-pool directeur mis à l’ampleur, équilibreur de charge matérielle
description: Résumé des certificats-pool directeur mis à l’ampleur, équilibreur de charge matérielle.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08abc37940cd41a29d6620cfc0a2a801de4a8e38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572230"
---
# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="f9780-103">Résumé des certificats-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9780-103">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9780-104">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="f9780-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f9780-105">Les certificats requis pour un directeur avec un programme d’équilibrage de la charge matérielle utiliseront un certificat par défaut dont le nom d’objet et les autres noms de sujet pour les services que le pool directeur peut recevoir.</span><span class="sxs-lookup"><span data-stu-id="f9780-105">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="f9780-106">Un certificat est demandé pour chaque directeur du pool.</span><span class="sxs-lookup"><span data-stu-id="f9780-106">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="f9780-107">En outre, un certificat de jeton OAuth pour les authentifications de serveur à serveur est installé sur chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="f9780-107">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="f9780-108">Certificats pour un directeur ayant fait l’objet d’une montée en charge via un appareil d’équilibrage de charge</span><span class="sxs-lookup"><span data-stu-id="f9780-108">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9780-109">Composant</span><span class="sxs-lookup"><span data-stu-id="f9780-109">Component</span></span></th>
<th><span data-ttu-id="f9780-110">Nom du sujet (SN)</span><span class="sxs-lookup"><span data-stu-id="f9780-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="f9780-111">Autres noms du sujet (SAN)</span><span class="sxs-lookup"><span data-stu-id="f9780-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="f9780-112">Comments</span><span class="sxs-lookup"><span data-stu-id="f9780-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9780-113">Par défaut</span><span class="sxs-lookup"><span data-stu-id="f9780-113">Default</span></span></p></td>
<td><p><span data-ttu-id="f9780-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9780-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f9780-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9780-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="f9780-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9780-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="f9780-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9780-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="f9780-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9780-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="f9780-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9780-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="f9780-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9780-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="f9780-121">(Facultatif) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9780-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9780-122">Les certificats directeurs peuvent être demandés auprès d’une autorité de certification gérée en interne ou auprès d’une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="f9780-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="f9780-123">Le directeur répond aux demandes du proxy inverse dans le périmètre ou à partir du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="f9780-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="f9780-124">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="f9780-124">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9780-125">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="f9780-125">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="f9780-126">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9780-126">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f9780-127">Aucune entrée</span><span class="sxs-lookup"><span data-stu-id="f9780-127">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="f9780-128">Notez que la longueur de clé minimale s’élève à 1 024 bits ; toutefois, vous pouvez recevoir un avertissement indiquant que la longueur de clé minimale recommandée s’élève à 2 048 bits.</span><span class="sxs-lookup"><span data-stu-id="f9780-128">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="f9780-p102">Le certificat OAuthTokenIssuer est un certificat à usage unique qui permet d’authentifier des serveurs dans un environnement à grande échelle ; il peut être demandé auprès d’une autorité de certification interne ou publique. Ce certificat est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="f9780-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

