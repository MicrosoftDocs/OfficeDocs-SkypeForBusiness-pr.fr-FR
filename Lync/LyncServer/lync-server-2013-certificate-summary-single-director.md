---
title: 'Lync Server 2013 : Résumé des certificats-directeur unique'
description: 'Lync Server 2013 : Résumé des certificats-directeur unique.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cf930a73d9989ec44f52f1d70ee9e0f900e4d6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572160"
---
# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="6b7e6-103">Résumé des certificats-directeur unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b7e6-103">Certificate summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b7e6-104">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6b7e6-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="6b7e6-105">Les certificats requis pour un seul directeur consistent en un certificat par défaut dont le nom d’objet et les autres noms de sujet pour les services que le directeur peut recevoir.</span><span class="sxs-lookup"><span data-stu-id="6b7e6-105">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="6b7e6-106">Il existe en outre un certificat de jeton OAuth servant à l’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="6b7e6-106">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="6b7e6-107">Certificats pour le directeur</span><span class="sxs-lookup"><span data-stu-id="6b7e6-107">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b7e6-108">Composant</span><span class="sxs-lookup"><span data-stu-id="6b7e6-108">Component</span></span></th>
<th><span data-ttu-id="6b7e6-109">Nom du sujet (SN)</span><span class="sxs-lookup"><span data-stu-id="6b7e6-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="6b7e6-110">Autres noms du sujet (SAN)</span><span class="sxs-lookup"><span data-stu-id="6b7e6-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="6b7e6-111">Comments</span><span class="sxs-lookup"><span data-stu-id="6b7e6-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b7e6-112">Par défaut</span><span class="sxs-lookup"><span data-stu-id="6b7e6-112">Default</span></span></p></td>
<td><p><span data-ttu-id="6b7e6-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6b7e6-113">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6b7e6-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6b7e6-114">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="6b7e6-115">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6b7e6-115">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="6b7e6-116">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6b7e6-116">meet.contoso.com</span></span></p>
<p><span data-ttu-id="6b7e6-117">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6b7e6-117">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="6b7e6-118">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6b7e6-118">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="6b7e6-119">(Facultatif) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6b7e6-119">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6b7e6-120">Les certificats directeurs peuvent être demandés auprès d’une autorité de certification gérée en interne ou auprès d’une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="6b7e6-120">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="6b7e6-121">Le directeur répond aux demandes du proxy inverse dans le périmètre ou à partir du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6b7e6-121">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="6b7e6-122">Les clients internes n’utiliseront pas le directeur.</span><span class="sxs-lookup"><span data-stu-id="6b7e6-122">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="6b7e6-123">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="6b7e6-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b7e6-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="6b7e6-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="6b7e6-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6b7e6-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6b7e6-126">Aucune entrée</span><span class="sxs-lookup"><span data-stu-id="6b7e6-126">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="6b7e6-127">Notez que la longueur de clé minimale s’élève à 1 024 bits ; toutefois, vous pouvez recevoir un avertissement indiquant que la longueur de clé minimale recommandée s’élève à 2 048 bits.</span><span class="sxs-lookup"><span data-stu-id="6b7e6-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="6b7e6-p103">Le certificat OAuthTokenIssuer est un certificat à usage unique qui permet d’authentifier des serveurs dans un environnement à grande échelle ; il peut être demandé auprès d’une autorité de certification interne ou publique. Ce certificat est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="6b7e6-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

