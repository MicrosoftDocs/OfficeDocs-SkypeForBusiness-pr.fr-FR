---
title: 'Lync Server 2013 : prise en charge de l’infrastructure DNS'
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
ms.openlocfilehash: b36437de04b3e7924085fe95b9f10b13e47cb867
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="fdbce-102">Prise en charge de l’infrastructure DNS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdbce-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdbce-103">_**Dernière modification de la rubrique :** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="fdbce-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="fdbce-104">Lync Server 2013 nécessite DNS (Domain Name System) et l’utilise de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="fdbce-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="fdbce-105">détecter les serveurs ou pools internes pour les communications de serveur à serveur ;</span><span class="sxs-lookup"><span data-stu-id="fdbce-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="fdbce-106">permettre aux clients de détecter le pool de serveurs frontaux ou le serveur Standard Edition utilisé pour diverses transactions SIP ;</span><span class="sxs-lookup"><span data-stu-id="fdbce-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="fdbce-107">associer les URL simples des conférences aux serveurs hébergeant ces conférences ;</span><span class="sxs-lookup"><span data-stu-id="fdbce-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="fdbce-108">permettre aux serveurs et clients externes de se connecter aux serveurs Edge ou au proxy inverse HTTP afin d’utiliser les fonctions de messagerie instantanée et de conférence ;</span><span class="sxs-lookup"><span data-stu-id="fdbce-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="fdbce-109">permettre aux périphériques de communications unifiées qui ne sont pas connectés de détecter le pool de serveurs frontaux ou le serveur Standard Edition exécutant le service web de mise à jour de périphériques, d’obtenir des mises à jour et d’envoyer des journaux ;</span><span class="sxs-lookup"><span data-stu-id="fdbce-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="fdbce-110">permettre aux clients mobiles de découvrir automatiquement les ressources de services web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres des périphériques.</span><span class="sxs-lookup"><span data-stu-id="fdbce-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="fdbce-111">procéder à l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="fdbce-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fdbce-112">Lync Server 2013 ne prend pas en charge les noms de domaine internationaux (IDN).</span><span class="sxs-lookup"><span data-stu-id="fdbce-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fdbce-113">Le nom que vous spécifiez doit être identique au nom d’ordinateur configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="fdbce-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="fdbce-114">Par défaut, le nom d’un ordinateur qui n’est pas membre d’un domaine est un nom court, et non un nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="fdbce-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="fdbce-115">Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts.</span><span class="sxs-lookup"><span data-stu-id="fdbce-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="fdbce-116">Par conséquent, vous devez configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non membre d’un domaine.</span><span class="sxs-lookup"><span data-stu-id="fdbce-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="fdbce-117"><STRONG>Utilisez uniquement des caractères standard</STRONG> (A–Z, a–z, 0–9 et tirets) lorsque vous assignez des noms de domaines complets à vos serveurs Lync, serveurs Edge et pools.</span><span class="sxs-lookup"><span data-stu-id="fdbce-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="fdbce-118">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="fdbce-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="fdbce-119">Les caractères non standard dans les noms de domaines complets ne sont généralement pas pris en charge par les DNS externes et les autorités publiques de certification (c’est-à-dire lorsque le nom de domaine complet doit être affecté à l’élément SN (Subject Name) du certificat).</span><span class="sxs-lookup"><span data-stu-id="fdbce-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

