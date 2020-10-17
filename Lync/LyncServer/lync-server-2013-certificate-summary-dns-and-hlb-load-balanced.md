---
title: 'Lync Server 2013 : Résumé des certificats-équilibrage de charge DNS et charge matérielle'
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
ms.openlocfilehash: 743818f81f5083e9c5d3a7877d2518d05176a5e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499291"
---
# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="73470-102">Résumé des certificats-charge DNS et charge matérielle équilibrée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73470-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73470-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="73470-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="73470-104">Certificate Requirements for a Director with DNS Load Balancing et un programme d’équilibrage de la charge matérielle utiliseront un certificat par défaut dont le nom d’objet et les autres noms de sujet pour les services que le directeur peut recevoir.</span><span class="sxs-lookup"><span data-stu-id="73470-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="73470-105">Un certificat est demandé pour chaque directeur du pool.</span><span class="sxs-lookup"><span data-stu-id="73470-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="73470-106">Il ne faut pas oublier que l’équilibreur de charge matérielle équilibre la charge uniquement pour le trafic du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="73470-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="73470-107">De plus, un certificat de jeton OAuth pour le processus d’authentification serveur à serveur existe qui est installé sur chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="73470-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="73470-108">Certificats pour le directeur</span><span class="sxs-lookup"><span data-stu-id="73470-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73470-109">Composant</span><span class="sxs-lookup"><span data-stu-id="73470-109">Component</span></span></th>
<th><span data-ttu-id="73470-110">Nom du sujet (SN)</span><span class="sxs-lookup"><span data-stu-id="73470-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="73470-111">Autres noms du sujet (SAN)</span><span class="sxs-lookup"><span data-stu-id="73470-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="73470-112">Comments</span><span class="sxs-lookup"><span data-stu-id="73470-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73470-113">Par défaut</span><span class="sxs-lookup"><span data-stu-id="73470-113">Default</span></span></p></td>
<td><p><span data-ttu-id="73470-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="73470-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="73470-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="73470-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="73470-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="73470-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="73470-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73470-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="73470-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73470-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="73470-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73470-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="73470-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73470-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="73470-121">(Facultatif) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73470-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73470-122">Les certificats directeurs peuvent être demandés auprès d’une autorité de certification gérée en interne ou auprès d’une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="73470-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="73470-123">Le directeur répond aux demandes du proxy inverse dans le périmètre ou à partir du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="73470-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="73470-124">Les clients internes n’utiliseront pas le directeur.</span><span class="sxs-lookup"><span data-stu-id="73470-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="73470-125">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="73470-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73470-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="73470-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="73470-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="73470-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="73470-128">Aucune entrée</span><span class="sxs-lookup"><span data-stu-id="73470-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="73470-129">Notez que la longueur de clé minimale s’élève à 1 024 bits ; toutefois, vous pouvez recevoir un avertissement indiquant que la longueur de clé minimale recommandée s’élève à 2 048 bits.</span><span class="sxs-lookup"><span data-stu-id="73470-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="73470-p103">Le certificat OAuthTokenIssuer est un certificat à usage unique qui permet d’authentifier des serveurs dans un environnement à grande échelle ; il peut être demandé auprès d’une autorité de certification interne ou publique. Ce certificat est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="73470-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

