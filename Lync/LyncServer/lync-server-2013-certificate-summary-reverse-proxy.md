---
title: 'Lync Server 2013 : Résumé des certificats - Proxy inverse'
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
ms.openlocfilehash: 42e52fa8522de53404fee3f3b5798f159361dbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="2897a-102">Résumé des certificats - Proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2897a-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2897a-103">_**Dernière modification de la rubrique :** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="2897a-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="2897a-104">Les exigences de certificat pour le proxy inverse sont beaucoup plus simples que celles des serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="2897a-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="2897a-105">L’organigramme fourni présente les exigences nécessaires.</span><span class="sxs-lookup"><span data-stu-id="2897a-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="2897a-106">La table associée présente le nom du sujet du certificat standard et les noms de remplacement de l’objet par rapport aux scénarios que nous avons examinés dans les discussions du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="2897a-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="2897a-107">Pour plus d’informations sur les scénarios de serveur Edge, voir [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2897a-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="2897a-108">**Diagramme de flux de certificats pour un proxy inverse**</span><span class="sxs-lookup"><span data-stu-id="2897a-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="2897a-109">![Diagramme de certificats pour le serveur Edge](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Diagramme de certificats pour le serveur Edge")</span><span class="sxs-lookup"><span data-stu-id="2897a-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="2897a-110">Proxy inverse : interface externe</span><span class="sxs-lookup"><span data-stu-id="2897a-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2897a-111">Composant</span><span class="sxs-lookup"><span data-stu-id="2897a-111">Component</span></span></th>
<th><span data-ttu-id="2897a-112">Nom de l’objet</span><span class="sxs-lookup"><span data-stu-id="2897a-112">Subject name</span></span></th>
<th><span data-ttu-id="2897a-113">Autre nom de l’objet (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="2897a-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="2897a-114">Commentaires</span><span class="sxs-lookup"><span data-stu-id="2897a-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2897a-115">Proxy inverse</span><span class="sxs-lookup"><span data-stu-id="2897a-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="2897a-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2897a-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2897a-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2897a-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="2897a-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2897a-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="2897a-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2897a-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="2897a-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2897a-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="2897a-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2897a-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="2897a-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2897a-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="2897a-123">(Facultatif) :\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="2897a-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2897a-124">Le certificat doit être émis par une autorité de certification publique et par l’utilisation améliorée du serveur.</span><span class="sxs-lookup"><span data-stu-id="2897a-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="2897a-125">Services : service de carnet d’adresses, extension de groupe de distribution applications Web Office pour les conférences et règles de publication de périphériques IP Lync.</span><span class="sxs-lookup"><span data-stu-id="2897a-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="2897a-126">Le nom alternatif de l’objet inclut :</span><span class="sxs-lookup"><span data-stu-id="2897a-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="2897a-127">Nom de domaine complet des services Web externes pour le serveur frontal ou le pool frontal</span><span class="sxs-lookup"><span data-stu-id="2897a-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="2897a-128">Nom de domaine complet des services Web externes pour le directeur ou le pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="2897a-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="2897a-129">Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="2897a-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="2897a-130">Règle de publication de réunion en ligne</span><span class="sxs-lookup"><span data-stu-id="2897a-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="2897a-131">Office Web Apps pour les conférences</span><span class="sxs-lookup"><span data-stu-id="2897a-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="2897a-132">Lyncdiscover (découverte automatique)</span><span class="sxs-lookup"><span data-stu-id="2897a-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="2897a-133">Le caractère générique facultatif remplace les SAN de connexion et de numérotation.</span><span class="sxs-lookup"><span data-stu-id="2897a-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

