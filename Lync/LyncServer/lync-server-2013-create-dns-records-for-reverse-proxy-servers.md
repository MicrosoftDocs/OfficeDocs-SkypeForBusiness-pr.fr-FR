---
title: 'Lync Server 2013 : créer des enregistrements DNS pour les serveurs proxy inverses'
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
ms.openlocfilehash: 60cd3033ae06f3fd9f0fc4a7a1e881f08f2ee90f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Créer des enregistrements DNS pour les serveurs proxy inverses dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-29_

Créez des enregistrements A DNS externe qui pointent vers l’interface externe publique de votre serveur Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 ou du routage de demande d’application Internet Information Server, comme décrit dans [configure DNS for Edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md). Vous avez besoin d’enregistrements DNS pour les noms de domaine complets des services Web externes pour chaque pool, le directeur (ou le pool directeur) et chaque URL simple.

Les enregistrements DNS minimum suivants doivent être créés pour la résolution client sur le proxy inverse :

  - Un ou plusieurs enregistrements hôte (A) qui définissent les services Web externes publiés pour les directeurs et les pools directeurs (par exemple, **webdirext.contoso.com**)

  - Un ou plusieurs enregistrements hôte (A) qui définissent les services Web externes publiés pour les services Web externes hébergés sur les pools frontaux et les rôles serveur Standard Edition (par exemple, **webext.contoso.com**)

  - Enregistrement hôte (A) pour les URL simples (par exemple, **dialin.contoso.com** et **meet.contoso.com**)

  - Enregistrement d’hôte (A) pour l’enregistrement externe Discover Lync et qui fournit également un pointeur vers autodiscover pour toutes les applications Web, y compris l’application Web Lync, le planificateur et la mobilité (par exemple, **lyncdiscover.contoso.com**)

  - Enregistrements d’hôte (A) pour l’URL Office Web Apps Server (par exemple, **officewebapp01.contoso.com**)

Pour plus d’informations, consultez la rubrique [DNS Summary-Reverse Proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

</div>

<span> </span>

</div>

</div>

</div>

