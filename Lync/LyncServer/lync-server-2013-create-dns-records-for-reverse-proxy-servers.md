---
title: 'Lync Server 2013 : créer des enregistrements DNS pour les serveurs proxy inverses'
description: 'Lync Server 2013 : créer des enregistrements DNS pour les serveurs proxy inverses.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef785ebbd7160274b631a2d2b6b1f1dcc866e5fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562280"
---
# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="7bfc9-103">Créer des enregistrements DNS pour les serveurs proxy inverses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bfc9-103">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bfc9-104">_**Dernière modification de la rubrique :** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="7bfc9-104">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="7bfc9-105">Créez des enregistrements A DNS externe qui pointent vers l’interface externe publique de votre serveur Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 ou du routage de demande d’application Internet Information Server, comme décrit dans [configure DNS for Edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span><span class="sxs-lookup"><span data-stu-id="7bfc9-105">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="7bfc9-106">Vous avez besoin d’enregistrements DNS pour les noms de domaine complets des services Web externes pour chaque pool, le directeur (ou le pool directeur) et chaque URL simple.</span><span class="sxs-lookup"><span data-stu-id="7bfc9-106">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="7bfc9-107">Les enregistrements DNS minimum suivants doivent être créés pour la résolution client sur le proxy inverse :</span><span class="sxs-lookup"><span data-stu-id="7bfc9-107">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="7bfc9-108">Un ou plusieurs enregistrements hôte (A) qui définissent les services Web externes publiés pour les directeurs et les pools directeurs (par exemple, **webdirext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="7bfc9-108">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="7bfc9-109">Un ou plusieurs enregistrements hôte (A) qui définissent les services Web externes publiés pour les services Web externes hébergés sur les pools frontaux et les rôles serveur Standard Edition (par exemple, **webext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="7bfc9-109">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="7bfc9-110">Enregistrement hôte (A) pour les URL simples (par exemple, **dialin.contoso.com** et **meet.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="7bfc9-110">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="7bfc9-111">Enregistrement d’hôte (A) pour l’enregistrement externe Discover Lync et qui fournit également un pointeur vers autodiscover pour toutes les applications Web, y compris l’application Web Lync, le planificateur et la mobilité (par exemple, **lyncdiscover.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="7bfc9-111">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="7bfc9-112">Enregistrements d’hôte (A) pour l’URL Office Web Apps Server (par exemple, **officewebapp01.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="7bfc9-112">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="7bfc9-113">Pour plus d’informations, consultez la rubrique [DNS Summary-Reverse Proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="7bfc9-113">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

