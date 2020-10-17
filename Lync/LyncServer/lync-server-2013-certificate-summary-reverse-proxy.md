---
title: 'Lync Server 2013 : Résumé des certificats-proxy inverse'
description: 'Lync Server 2013 : Résumé des certificats-proxy inverse.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc250d6de2eb1a0b6c3ad3495c8df62942f9a81
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572300"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="90ebb-103">Résumé des certificats-proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90ebb-103">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90ebb-104">_**Dernière modification de la rubrique :** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="90ebb-104">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="90ebb-105">Les exigences de certificat pour le proxy inverse sont plus simples que celles des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="90ebb-105">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="90ebb-106">Le diagramme de flux fourni présente les conditions requises.</span><span class="sxs-lookup"><span data-stu-id="90ebb-106">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="90ebb-107">Le tableau associé présente le nom de sujet du certificat et les autres noms du sujet par rapport aux scénarios que nous avons consultés dans les discussions de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="90ebb-107">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="90ebb-108">Pour plus d’informations sur les scénarios de serveur Edge, voir [Scenarios for External User Access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="90ebb-108">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="90ebb-109">**Organigramme des certificats pour le proxy inverse**</span><span class="sxs-lookup"><span data-stu-id="90ebb-109">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="90ebb-110">![Organigramme des certificats pour le serveur Edge](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Organigramme des certificats pour le serveur Edge")</span><span class="sxs-lookup"><span data-stu-id="90ebb-110">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="90ebb-111">Proxy inverse : interface externe</span><span class="sxs-lookup"><span data-stu-id="90ebb-111">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90ebb-112">Composant</span><span class="sxs-lookup"><span data-stu-id="90ebb-112">Component</span></span></th>
<th><span data-ttu-id="90ebb-113">Nom du sujet</span><span class="sxs-lookup"><span data-stu-id="90ebb-113">Subject name</span></span></th>
<th><span data-ttu-id="90ebb-114">Autre nom de l’objet (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="90ebb-114">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="90ebb-115">Comments</span><span class="sxs-lookup"><span data-stu-id="90ebb-115">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90ebb-116">Proxy inverse</span><span class="sxs-lookup"><span data-stu-id="90ebb-116">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="90ebb-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90ebb-117">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="90ebb-118">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90ebb-118">webext.contoso.com</span></span></p>
<p><span data-ttu-id="90ebb-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90ebb-119">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="90ebb-120">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90ebb-120">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="90ebb-121">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90ebb-121">meet.contoso.com</span></span></p>
<p><span data-ttu-id="90ebb-122">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90ebb-122">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="90ebb-123">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90ebb-123">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="90ebb-124">(Facultatif) :\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="90ebb-124">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="90ebb-125">Le certificat doit être émis par une autorité de certification publique et avec l’utilisation améliorée de l’extension serveur.</span><span class="sxs-lookup"><span data-stu-id="90ebb-125">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="90ebb-126">Les services incluent le service de carnet d’adresses, le développement de groupes de distribution Office Web Apps pour les conférences et les règles de publication d’appareils IP Lync.</span><span class="sxs-lookup"><span data-stu-id="90ebb-126">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="90ebb-127">Les autres noms de sujet incluent :</span><span class="sxs-lookup"><span data-stu-id="90ebb-127">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="90ebb-128">Nom de domaine complet externe des services Web pour le serveur frontal ou le pool frontal</span><span class="sxs-lookup"><span data-stu-id="90ebb-128">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="90ebb-129">Nom de domaine complet externe des services Web pour le directeur ou le pool directeur</span><span class="sxs-lookup"><span data-stu-id="90ebb-129">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="90ebb-130">Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="90ebb-130">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="90ebb-131">Règle de publication de réunion en ligne</span><span class="sxs-lookup"><span data-stu-id="90ebb-131">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="90ebb-132">Office Web Apps pour les conférences</span><span class="sxs-lookup"><span data-stu-id="90ebb-132">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="90ebb-133">Lyncdiscover (découverte automatique)</span><span class="sxs-lookup"><span data-stu-id="90ebb-133">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="90ebb-134">Le caractère générique facultatif remplace le SAN de conférence et de numérotation.</span><span class="sxs-lookup"><span data-stu-id="90ebb-134">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

