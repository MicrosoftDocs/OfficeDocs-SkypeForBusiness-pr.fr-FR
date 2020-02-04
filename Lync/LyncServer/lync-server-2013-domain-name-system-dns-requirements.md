---
title: 'Configuration requise pour Lync Server 2013 : DNS (Domain Name System)'
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
ms.openlocfilehash: 2eddf86c881875ebbe08fddd6ffa85403dda6b60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="d516b-102">Configuration requise pour le service DNS (Domain Name System) pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d516b-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d516b-103">_**Dernière modification de la rubrique :** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="d516b-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="d516b-104">Pour déployer Lync Server, vous devez créer des enregistrements DNS (Domain Name System) qui autorisent la découverte de clients et de serveurs et, éventuellement, la prise en charge de la connexion automatique du client si votre organisation veut le prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="d516b-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="d516b-105">Lync Server utilise le DNS de l’une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="d516b-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="d516b-106">Pour découvrir les serveurs internes ou les pools de communications serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="d516b-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="d516b-107">Pour permettre aux clients de découvrir le pool frontal ou le serveur Standard Edition utilisé pour différentes transactions SIP.</span><span class="sxs-lookup"><span data-stu-id="d516b-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="d516b-108">Pour autoriser les appareils de communications unifiées (UC) qui ne sont pas connectés à un appareil pour découvrir le pool frontal ou le serveur Standard Edition Web exécutant la mise à jour des appareils, obtenez les mises à jour et envoyez les journaux.</span><span class="sxs-lookup"><span data-stu-id="d516b-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="d516b-109">Pour permettre à des serveurs et clients externes de se connecter à des serveurs Edge ou au proxy HTTP inverse pour la messagerie instantanée ou les conférences.</span><span class="sxs-lookup"><span data-stu-id="d516b-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="d516b-110">Pour autoriser les appareils à UC externes à se connecter à un service Web de mise à jour d’appareil via des serveurs Edge ou le proxy HTTP inverse, et obtenir des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="d516b-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="d516b-111">Pour permettre aux clients mobiles de détecter automatiquement les ressources de services Web sans exiger l’entrée manuelle des URL dans les paramètres de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="d516b-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d516b-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d516b-112">In This Section</span></span>

  - [<span data-ttu-id="d516b-113">Détermination de la configuration requise pour DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d516b-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="d516b-114">Configuration DNS requise pour les listes frontales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d516b-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="d516b-115">Configuration DNS requise pour les serveurs Standard Edition Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d516b-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="d516b-116">Enregistrements DNS requis pour les URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d516b-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="d516b-117">Configuration DNS requise pour la connexion automatique au client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d516b-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="d516b-118">Configuration DNS requise pour la mobilité avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d516b-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="d516b-119">Équilibrage de charge DNS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d516b-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

