---
title: 'Lync Server 2013 : configuration requise pour DNS (Domain Name System)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2536e5079009d508765055d31e80efb1b998aa0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="7ebf6-102">Configuration requise pour le système DNS (Domain Name System) pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ebf6-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ebf6-103">_**Dernière modification de la rubrique :** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="7ebf6-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="7ebf6-104">Pour déployer Lync Server, vous devez créer des enregistrements DNS (Domain Name System) qui activent la découverte des clients et des serveurs, et, éventuellement, la prise en charge de la connexion automatique des clients si votre organisation souhaite la prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="7ebf6-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="7ebf6-105">Lync Server utilise le système DNS des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="7ebf6-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="7ebf6-106">détecter les serveurs ou pools internes pour les communications de serveur à serveur ;</span><span class="sxs-lookup"><span data-stu-id="7ebf6-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="7ebf6-107">Pour permettre aux clients de détecter le pool frontal ou le serveur Standard Edition utilisé pour diverses transactions SIP ;</span><span class="sxs-lookup"><span data-stu-id="7ebf6-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="7ebf6-108">Pour autoriser les périphériques de communications unifiées qui ne sont pas connectés pour découvrir le pool frontal ou le serveur Standard Edition exécutant le service Web de mise à jour des périphériques, récupérez les mises à jour et envoyez des journaux.</span><span class="sxs-lookup"><span data-stu-id="7ebf6-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="7ebf6-109">Pour permettre aux serveurs et clients externes de se connecter aux serveurs Edge ou au proxy inverse HTTP pour la messagerie instantanée ou la Conférence.</span><span class="sxs-lookup"><span data-stu-id="7ebf6-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="7ebf6-110">Pour permettre aux périphériques de communications unifiées externes de se connecter au service Web de mise à jour des périphériques via les serveurs Edge ou le proxy inverse HTTP et d’obtenir des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="7ebf6-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="7ebf6-111">pour permettre aux clients mobiles de découvrir automatiquement les ressources de services web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres des appareils.</span><span class="sxs-lookup"><span data-stu-id="7ebf6-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7ebf6-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7ebf6-112">In This Section</span></span>

  - [<span data-ttu-id="7ebf6-113">Déterminer les exigences DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ebf6-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="7ebf6-114">Configuration DNS requise pour les pools frontaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ebf6-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="7ebf6-115">Configuration DNS requise pour les serveurs Standard Edition Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ebf6-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="7ebf6-116">Configuration DNS requise pour les URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ebf6-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="7ebf6-117">Configuration DNS requise pour la connexion automatique des clients dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ebf6-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="7ebf6-118">Configuration DNS requise pour la mobilité avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ebf6-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="7ebf6-119">Équilibrage de la charge DNS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ebf6-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

