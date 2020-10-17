---
title: Résumé des ports-Fédération XMPP (extensible Messaging and Presence Protocol)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c8d7f99b4a7c72b9eb039fb7447397e711caa36
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527921"
---
# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="bc1b7-102">Résumé des ports-Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc1b7-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc1b7-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="bc1b7-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="bc1b7-104">Les ports et protocoles définis pour le proxy XMPP (extensible Messaging and Presence Protocol) déployé sur le serveur Edge autorisent les communications du partenaire fédéré XMPP au serveur Edge et permettent également la communication entre votre serveur Edge et le partenaire fédéré XMPP.</span><span class="sxs-lookup"><span data-stu-id="bc1b7-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="bc1b7-105">Une règle est également définie sur le pare-feu orienté vers l’intérieur du serveur frontal ou du pool frontal vers le serveur Edge ou le pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="bc1b7-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="bc1b7-106">Résumé du pare-feu pour le protocole XMPP</span><span class="sxs-lookup"><span data-stu-id="bc1b7-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc1b7-107">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="bc1b7-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="bc1b7-108">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="bc1b7-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="bc1b7-109">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="bc1b7-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="bc1b7-110">Comments</span><span class="sxs-lookup"><span data-stu-id="bc1b7-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc1b7-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="bc1b7-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="bc1b7-112">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="bc1b7-112">Any</span></span></p></td>
<td><p><span data-ttu-id="bc1b7-113">Adresse IP de l’interface du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="bc1b7-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="bc1b7-114">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="bc1b7-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="bc1b7-115">Autorise la communication vers le proxy XMPP du serveur Edge à partir de partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="bc1b7-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc1b7-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="bc1b7-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="bc1b7-117">Adresse IP de l’interface du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="bc1b7-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="bc1b7-118">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="bc1b7-118">Any</span></span></p></td>
<td><p><span data-ttu-id="bc1b7-119">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="bc1b7-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="bc1b7-120">Autorise la communication du proxy XMPP serveur Edge aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="bc1b7-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc1b7-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="bc1b7-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="bc1b7-122">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="bc1b7-122">Any</span></span></p></td>
<td><p><span data-ttu-id="bc1b7-123">Adresse IP de l’interface du serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="bc1b7-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="bc1b7-124">Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool frontal vers le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="bc1b7-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc1b7-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc1b7-125">See Also</span></span>


[<span data-ttu-id="bc1b7-126">Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk</span><span class="sxs-lookup"><span data-stu-id="bc1b7-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="bc1b7-127">Gérer les partenaires fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc1b7-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

