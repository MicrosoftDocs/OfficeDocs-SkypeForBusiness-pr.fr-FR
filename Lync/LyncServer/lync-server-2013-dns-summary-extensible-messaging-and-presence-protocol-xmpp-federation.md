---
title: Service de synthèse DNS-extensibilité du protocole de messagerie et de présence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff58998ef9114baeb7dc7c6462ca0ebaae114f10
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="03765-102">Service DNS Summary-extensible Messaging and Presence Protocol (XMPP) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03765-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03765-103">_**Dernière modification de la rubrique:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="03765-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="03765-104">Pour configurer le protocole XMPP (extensible Messaging and Presence Protocol) pour votre déploiement, vous devez créer deux enregistrements DNS (Domain Name System) dans un serveur DNS externe qui résoudra les enregistrements au service Edge d’accès de votre serveur Edge ou de votre pool Edge.</span><span class="sxs-lookup"><span data-stu-id="03765-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="03765-105">DNS Summary pour le protocole de messagerie et de présence extensible</span><span class="sxs-lookup"><span data-stu-id="03765-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03765-106">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="03765-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="03765-107">FQDN</span><span class="sxs-lookup"><span data-stu-id="03765-107">FQDN</span></span></th>
<th><span data-ttu-id="03765-108">Enregistrement d’adresse IP/nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="03765-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="03765-109">Cartes sur/Commentaires</span><span class="sxs-lookup"><span data-stu-id="03765-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03765-110">DNS externe/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="03765-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="03765-111">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03765-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="03765-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03765-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="03765-113">Interface externe du proxy XMPP du service Edge d’accès ou du pool Edge. Répétez cette opération pour tous les domaines SIP internes avec Lync pour les utilisateurs pour lesquels le contact avec les contacts XMPP est autorisé via la configuration de la stratégie d’accès externe par le biais d’une stratégie globale, d’une stratégie de site à l’emplacement de l’utilisateur ou d’une stratégie utilisateur appliquée au Utilisateur compatible Lync.</span><span class="sxs-lookup"><span data-stu-id="03765-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="03765-114">Un domaine XMPP autorisé doit également être configuré dans la stratégie partenaires fédérés de XMPP.</span><span class="sxs-lookup"><span data-stu-id="03765-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="03765-115">Pour plus d’informations, voir rubriques supplémentaires dans la <strong>section Voir aussi</strong> .</span><span class="sxs-lookup"><span data-stu-id="03765-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03765-116">DNS/A externe</span><span class="sxs-lookup"><span data-stu-id="03765-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="03765-117">xmpp.contoso.com (par exemple)</span><span class="sxs-lookup"><span data-stu-id="03765-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="03765-118">Adresse IP du service Edge d’accès sur votre serveur Edge ou pool d’hébergement de proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="03765-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="03765-119">Pointe vers le service Edge d’accès ou le pool Edge qui héberge le service proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="03765-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="03765-120">En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA).</span><span class="sxs-lookup"><span data-stu-id="03765-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03765-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="03765-121">See Also</span></span>


[<span data-ttu-id="03765-122">Configuration de la fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03765-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="03765-123">Détermination de la configuration requise pour DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03765-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

