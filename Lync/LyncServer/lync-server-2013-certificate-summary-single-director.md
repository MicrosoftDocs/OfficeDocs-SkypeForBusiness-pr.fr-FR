---
title: 'Lync Server 2013 : Résumé des certificats - Directeur unique'
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
ms.openlocfilehash: f18fcec270104be1620402ddee0c665c0f3f3a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="2bcc7-102">Résumé des certificats - Directeur unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bcc7-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bcc7-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2bcc7-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2bcc7-104">Les exigences en matière de certificat pour un seul directeur sont composées d’un certificat par défaut dont le nom du sujet comporte le nom de l’objet et des noms de remplacement pour les services que le directeur peut recevoir.</span><span class="sxs-lookup"><span data-stu-id="2bcc7-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="2bcc7-105">Par ailleurs, il existe un certificat de jeton OAuth pour les besoins d’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="2bcc7-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="2bcc7-106">Certificats pour Director</span><span class="sxs-lookup"><span data-stu-id="2bcc7-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2bcc7-107">Composant</span><span class="sxs-lookup"><span data-stu-id="2bcc7-107">Component</span></span></th>
<th><span data-ttu-id="2bcc7-108">Nom du sujet (SN)</span><span class="sxs-lookup"><span data-stu-id="2bcc7-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="2bcc7-109">Autres noms d’objet (SAN)</span><span class="sxs-lookup"><span data-stu-id="2bcc7-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="2bcc7-110">Commentaires</span><span class="sxs-lookup"><span data-stu-id="2bcc7-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2bcc7-111">Par défaut</span><span class="sxs-lookup"><span data-stu-id="2bcc7-111">Default</span></span></p></td>
<td><p><span data-ttu-id="2bcc7-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2bcc7-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2bcc7-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2bcc7-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="2bcc7-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2bcc7-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="2bcc7-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2bcc7-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="2bcc7-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2bcc7-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="2bcc7-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2bcc7-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="2bcc7-118">(Facultatif) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="2bcc7-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2bcc7-119">Les certificats de réalisateur peuvent être demandés auprès d’une autorité de certification (CA) gérée en interne ou auprès d’une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="2bcc7-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="2bcc7-120">Le directeur répond aux requêtes du proxy inverse dans le périmètre ou du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="2bcc7-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="2bcc7-121">Les clients internes n’utiliseront pas le directeur.</span><span class="sxs-lookup"><span data-stu-id="2bcc7-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="2bcc7-122">Ou une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="2bcc7-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bcc7-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="2bcc7-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="2bcc7-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2bcc7-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2bcc7-125">Aucune entrée</span><span class="sxs-lookup"><span data-stu-id="2bcc7-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="2bcc7-126">Notez que la longueur de la clé minimum est de 1024, mais vous pouvez recevoir un avertissement indiquant que la longueur de la clé minimum recommandée est 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="2bcc7-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="2bcc7-127">Le certificat OAuthTokenIssuer est un certificat à usage unique qui permet d’authentifier des serveurs dans un environnement à grande échelle et qui peut être demandé auprès d’une autorité de certification interne ou d’une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="2bcc7-127">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="2bcc7-128">Le certificat est requis.</span><span class="sxs-lookup"><span data-stu-id="2bcc7-128">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

