---
title: 'Lync Server 2013 : Résumé des certificats - Équilibrage de charge DNS et matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8cd6d86844629544b54670eb07c3433d19f99f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="03472-102">Résumé des certificats - Équilibrage de charge DNS et matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03472-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03472-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="03472-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="03472-104">Les exigences en matière de certificat pour un directeur avec l’équilibrage de charge DNS et un équilibreur de charge matérielle utilise un certificat par défaut qui comporte un nom de sujet et des noms de remplacement d’objet pour les services que le directeur peut recevoir.</span><span class="sxs-lookup"><span data-stu-id="03472-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="03472-105">Un certificat est demandé pour chaque réalisateur du pool.</span><span class="sxs-lookup"><span data-stu-id="03472-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="03472-106">Il est important de se souvenir que le service d’équilibrage de la charge matérielle ne charge que le trafic du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="03472-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="03472-107">Par ailleurs, il existe un certificat de jeton OAuth pour les rôles d’authentification de serveur à serveur qui est installé sur chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="03472-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="03472-108">Certificats pour Director</span><span class="sxs-lookup"><span data-stu-id="03472-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03472-109">Composant</span><span class="sxs-lookup"><span data-stu-id="03472-109">Component</span></span></th>
<th><span data-ttu-id="03472-110">Nom du sujet (SN)</span><span class="sxs-lookup"><span data-stu-id="03472-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="03472-111">Autres noms d’objet (SAN)</span><span class="sxs-lookup"><span data-stu-id="03472-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="03472-112">Commentaires</span><span class="sxs-lookup"><span data-stu-id="03472-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03472-113">Par défaut</span><span class="sxs-lookup"><span data-stu-id="03472-113">Default</span></span></p></td>
<td><p><span data-ttu-id="03472-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="03472-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="03472-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="03472-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="03472-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="03472-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="03472-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03472-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="03472-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03472-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="03472-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03472-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="03472-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03472-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="03472-121">(Facultatif) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="03472-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="03472-122">Les certificats de réalisateur peuvent être demandés auprès d’une autorité de certification (CA) gérée en interne ou auprès d’une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="03472-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="03472-123">Le directeur répond aux requêtes du proxy inverse dans le périmètre ou du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="03472-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="03472-124">Les clients internes n’utiliseront pas le directeur.</span><span class="sxs-lookup"><span data-stu-id="03472-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="03472-125">Ou une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="03472-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03472-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="03472-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="03472-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="03472-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="03472-128">Aucune entrée</span><span class="sxs-lookup"><span data-stu-id="03472-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="03472-129">Notez que la longueur de la clé minimum est de 1024, mais vous pouvez recevoir un avertissement indiquant que la longueur de la clé minimum recommandée est 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="03472-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="03472-130">Le certificat OAuthTokenIssuer est un certificat à usage unique qui permet d’authentifier des serveurs dans un environnement à grande échelle et qui peut être demandé auprès d’une autorité de certification interne ou d’une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="03472-130">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="03472-131">Le certificat est requis.</span><span class="sxs-lookup"><span data-stu-id="03472-131">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

