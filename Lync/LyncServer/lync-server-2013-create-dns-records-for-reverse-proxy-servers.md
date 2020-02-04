---
title: 'Lync Server 2013 : Création des enregistrements DNS pour les serveurs proxy inverses'
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
ms.openlocfilehash: 0f85b222688dcefd45030f2c05f7b59ce45ec0ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="7447b-102">Création des enregistrements DNS pour les serveurs proxy inverses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7447b-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7447b-103">_**Dernière modification de la rubrique :** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="7447b-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="7447b-104">Créer un DNS externe un enregistrement qui pointe vers l’interface externe publique de votre serveur Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, de la passerelle de gestion des menaces Forefront 2010 ou du routage [2013 de](lync-server-2013-configure-dns-for-edge-support.md)requête sur Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="7447b-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="7447b-105">Vous avez besoin d’enregistrements DNS pour les noms de domaine complets des services Web externes de chaque liste, le directeur (ou le pool de directeurs) et chaque URL simple.</span><span class="sxs-lookup"><span data-stu-id="7447b-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="7447b-106">Les enregistrements DNS minimaux pour la résolution du client vers le proxy inverse, les enregistrements suivants doivent être créés :</span><span class="sxs-lookup"><span data-stu-id="7447b-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="7447b-107">Un ou plusieurs enregistrements d’hôte qui définissent les services Web externes publiés pour les directeurs et les pools de directeurs (par exemple, **webdirext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="7447b-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="7447b-108">Un ou plusieurs enregistrements d’hôte (A) qui définissent les services Web externes publiés pour les services Web externes hébergés sur les pools frontaux et les rôles de serveur Standard Edition (par exemple, **webext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="7447b-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="7447b-109">Des enregistrements d’hôte (A) pour les URL simples (par exemple, **Dialin.contoso.com** et **Meet.contoso.com**);</span><span class="sxs-lookup"><span data-stu-id="7447b-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="7447b-110">L’enregistrement d’hôte (A) pour l’enregistrement externe Discover Lync et fournit également un pointeur vers la découverte automatique pour toutes les applications Web, y compris Lync Web App, le planificateur et la mobilité (par exemple, **lyncdiscover.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="7447b-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="7447b-111">Les enregistrements d’hôte (A) pour l’URL du serveur Office Web Apps (par exemple, **officewebapp01.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="7447b-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="7447b-112">Pour plus d’informations, reportez-vous à la section [DNS Summary-inverse dans Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="7447b-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

