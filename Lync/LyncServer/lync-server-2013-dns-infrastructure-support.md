---
title: 'Lync Server 2013 : Prise en charge des infrastructures DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d192388d03bb96a5d630a230ab4bd35e22c3217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="d8637-102">Prise en charge des infrastructures DNS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8637-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8637-103">_**Dernière modification de la rubrique :** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="d8637-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="d8637-104">Lync Server 2013 nécessite DNS (Domain Name System) et l’utilise comme suit :</span><span class="sxs-lookup"><span data-stu-id="d8637-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="d8637-105">Pour découvrir les serveurs internes ou les pools de communications serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="d8637-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="d8637-106">Pour permettre aux clients de découvrir le pool frontal ou le serveur Standard Edition utilisé pour différentes transactions SIP.</span><span class="sxs-lookup"><span data-stu-id="d8637-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="d8637-107">Pour associer les URL simples aux conférences avec les serveurs hébergeant ces conférences.</span><span class="sxs-lookup"><span data-stu-id="d8637-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="d8637-108">Pour permettre à des serveurs et clients externes de se connecter à des serveurs Edge ou au proxy HTTP inverse pour la messagerie instantanée ou les conférences.</span><span class="sxs-lookup"><span data-stu-id="d8637-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="d8637-109">Pour activer les appareils de communications unifiées (UC) qui ne sont pas connectés pour détecter le pool frontal ou le serveur Standard Edition Web exécutant des mises à jour de périphériques, obtenez des mises à jour et envoyez des journaux.</span><span class="sxs-lookup"><span data-stu-id="d8637-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="d8637-110">Pour permettre aux clients mobiles de détecter automatiquement les ressources de services Web sans exiger l’entrée manuelle des URL dans les paramètres de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="d8637-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="d8637-111">Pour l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="d8637-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8637-112">Lync Server 2013 ne prend pas en charge les noms de domaines internationaux (IDNs).</span><span class="sxs-lookup"><span data-stu-id="d8637-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d8637-113">Le nom spécifié doit être identique au nom de l’ordinateur configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="d8637-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="d8637-114">Par défaut, le nom d’un ordinateur qui n’est pas lié à un domaine est un nom court, pas un nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="d8637-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="d8637-115">Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts.</span><span class="sxs-lookup"><span data-stu-id="d8637-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="d8637-116">Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur qui sera déployé en tant que serveur de périphérie non lié à un domaine.</span><span class="sxs-lookup"><span data-stu-id="d8637-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="d8637-117"><STRONG>Utilisez uniquement les caractères standard</STRONG> (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous assignez les FQDN de vos serveurs Lync, serveurs de périphérie et pools.</span><span class="sxs-lookup"><span data-stu-id="d8637-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="d8637-118">N’utilisez pas les caractères ou traits de soulignement Unicode.</span><span class="sxs-lookup"><span data-stu-id="d8637-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="d8637-119">Souvent, les caractères non standard dans un FQDN ne sont pas pris en charge par le DNS externe et les autorités de certification publique (quand le FQDN doit être assigné au SN dans le certificat).</span><span class="sxs-lookup"><span data-stu-id="d8637-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

