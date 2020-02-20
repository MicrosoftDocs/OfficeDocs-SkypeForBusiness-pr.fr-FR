---
title: Résumé des certificats-pool directeur mis à l’ampleur, équilibreur de charge matérielle
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
ms.openlocfilehash: 59adcaf94c3c4364c6bb62ce2b8cbcc5639af6b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="260df-102">Résumé des certificats-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="260df-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="260df-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="260df-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="260df-104">Les certificats requis pour un directeur avec un programme d’équilibrage de la charge matérielle utiliseront un certificat par défaut dont le nom d’objet et les autres noms de sujet pour les services que le pool directeur peut recevoir.</span><span class="sxs-lookup"><span data-stu-id="260df-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="260df-105">Un certificat est demandé pour chaque directeur du pool.</span><span class="sxs-lookup"><span data-stu-id="260df-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="260df-106">En outre, un certificat de jeton OAuth pour les authentifications de serveur à serveur est installé sur chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="260df-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="260df-107">Certificats pour un directeur ayant fait l’objet d’une montée en charge via un appareil d’équilibrage de charge</span><span class="sxs-lookup"><span data-stu-id="260df-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="260df-108">Composant</span><span class="sxs-lookup"><span data-stu-id="260df-108">Component</span></span></th>
<th><span data-ttu-id="260df-109">Nom du sujet (SN)</span><span class="sxs-lookup"><span data-stu-id="260df-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="260df-110">Autres noms du sujet (SAN)</span><span class="sxs-lookup"><span data-stu-id="260df-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="260df-111">Commentaires</span><span class="sxs-lookup"><span data-stu-id="260df-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="260df-112">Par défaut</span><span class="sxs-lookup"><span data-stu-id="260df-112">Default</span></span></p></td>
<td><p><span data-ttu-id="260df-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="260df-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="260df-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="260df-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="260df-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="260df-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="260df-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="260df-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="260df-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="260df-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="260df-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="260df-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="260df-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="260df-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="260df-120">(Facultatif) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="260df-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="260df-121">Les certificats directeurs peuvent être demandés auprès d’une autorité de certification gérée en interne ou auprès d’une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="260df-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="260df-122">Le directeur répond aux demandes du proxy inverse dans le périmètre ou à partir du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="260df-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="260df-123">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="260df-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="260df-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="260df-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="260df-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="260df-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="260df-126">Aucune entrée</span><span class="sxs-lookup"><span data-stu-id="260df-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="260df-127">Notez que la longueur de clé minimale s’élève à 1 024 bits ; toutefois, vous pouvez recevoir un avertissement indiquant que la longueur de clé minimale recommandée s’élève à 2 048 bits.</span><span class="sxs-lookup"><span data-stu-id="260df-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="260df-p102">Le certificat OAuthTokenIssuer est un certificat à usage unique qui permet d’authentifier des serveurs dans un environnement à grande échelle ; il peut être demandé auprès d’une autorité de certification interne ou publique. Ce certificat est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="260df-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

