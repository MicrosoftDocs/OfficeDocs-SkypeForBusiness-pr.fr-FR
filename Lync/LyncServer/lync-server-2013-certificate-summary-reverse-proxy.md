---
title: 'Lync Server 2013 : Résumé des certificats-proxy inverse'
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
ms.openlocfilehash: 56da4c10da99a43c3a93f9ae251c2eb6f1536b37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="348cb-102">Résumé des certificats-proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="348cb-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="348cb-103">_**Dernière modification de la rubrique :** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="348cb-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="348cb-104">Les exigences de certificat pour le proxy inverse sont plus simples que celles des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="348cb-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="348cb-105">Le diagramme de flux fourni présente les conditions requises.</span><span class="sxs-lookup"><span data-stu-id="348cb-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="348cb-106">Le tableau associé présente le nom de sujet du certificat et les autres noms du sujet par rapport aux scénarios que nous avons consultés dans les discussions de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="348cb-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="348cb-107">Pour plus d’informations sur les scénarios de serveur Edge, voir [Scenarios for External User Access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="348cb-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="348cb-108">**Organigramme des certificats pour le proxy inverse**</span><span class="sxs-lookup"><span data-stu-id="348cb-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="348cb-109">![Organigramme des certificats pour le serveur Edge](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Organigramme des certificats pour le serveur Edge")</span><span class="sxs-lookup"><span data-stu-id="348cb-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="348cb-110">Proxy inverse : interface externe</span><span class="sxs-lookup"><span data-stu-id="348cb-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="348cb-111">Composant</span><span class="sxs-lookup"><span data-stu-id="348cb-111">Component</span></span></th>
<th><span data-ttu-id="348cb-112">Nom du sujet</span><span class="sxs-lookup"><span data-stu-id="348cb-112">Subject name</span></span></th>
<th><span data-ttu-id="348cb-113">Autre nom de l’objet (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="348cb-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="348cb-114">Commentaires</span><span class="sxs-lookup"><span data-stu-id="348cb-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="348cb-115">Proxy inverse</span><span class="sxs-lookup"><span data-stu-id="348cb-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="348cb-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="348cb-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="348cb-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="348cb-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="348cb-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="348cb-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="348cb-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="348cb-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="348cb-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="348cb-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="348cb-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="348cb-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="348cb-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="348cb-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="348cb-123">(Facultatif) :\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="348cb-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="348cb-124">Le certificat doit être émis par une autorité de certification publique et avec l’utilisation améliorée de l’extension serveur.</span><span class="sxs-lookup"><span data-stu-id="348cb-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="348cb-125">Les services incluent le service de carnet d’adresses, le développement de groupes de distribution Office Web Apps pour les conférences et les règles de publication d’appareils IP Lync.</span><span class="sxs-lookup"><span data-stu-id="348cb-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="348cb-126">Les autres noms de sujet incluent :</span><span class="sxs-lookup"><span data-stu-id="348cb-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="348cb-127">Nom de domaine complet externe des services Web pour le serveur frontal ou le pool frontal</span><span class="sxs-lookup"><span data-stu-id="348cb-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="348cb-128">Nom de domaine complet externe des services Web pour le directeur ou le pool directeur</span><span class="sxs-lookup"><span data-stu-id="348cb-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="348cb-129">Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="348cb-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="348cb-130">Règle de publication de réunion en ligne</span><span class="sxs-lookup"><span data-stu-id="348cb-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="348cb-131">Office Web Apps pour les conférences</span><span class="sxs-lookup"><span data-stu-id="348cb-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="348cb-132">Lyncdiscover (découverte automatique)</span><span class="sxs-lookup"><span data-stu-id="348cb-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="348cb-133">Le caractère générique facultatif remplace le SAN de conférence et de numérotation.</span><span class="sxs-lookup"><span data-stu-id="348cb-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

