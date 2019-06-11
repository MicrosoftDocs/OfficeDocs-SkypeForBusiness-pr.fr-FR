---
title: Résumé de port-Fédération de protocoles de messagerie extensible et de présence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b36a74393a8c61d5281bb009d212ee0bb12cf0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="10a22-102">Service de synthèse de port-extension de messagerie (XMPP) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10a22-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10a22-103">_**Dernière modification de la rubrique:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="10a22-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="10a22-104">Les ports et protocoles définis pour le proxy d’extension de messagerie et de présence (XMPP) déployés sur le serveur Edge autorisent les communications du partenaire fédéré de XMPP au serveur Edge et permettent également la communication entre votre serveur Edge et la fonction XMPP. partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="10a22-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="10a22-105">Une règle est également définie pour le pare-feu à l’intérieur du serveur frontal ou du pool frontal du serveur Edge ou du pool Edge.</span><span class="sxs-lookup"><span data-stu-id="10a22-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="10a22-106">Résumé du pare-feu pour le protocole extensible de messagerie et de présence</span><span class="sxs-lookup"><span data-stu-id="10a22-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10a22-107">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="10a22-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="10a22-108">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="10a22-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="10a22-109">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="10a22-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="10a22-110">Commentaires</span><span class="sxs-lookup"><span data-stu-id="10a22-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10a22-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="10a22-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="10a22-112">Indifférente</span><span class="sxs-lookup"><span data-stu-id="10a22-112">Any</span></span></p></td>
<td><p><span data-ttu-id="10a22-113">Adresse IP de l’interface du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="10a22-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="10a22-114">Port de communication serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="10a22-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="10a22-115">Autorise la communication au proxy de serveur Edge XMPP auprès des partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="10a22-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10a22-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="10a22-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="10a22-117">Adresse IP de l’interface du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="10a22-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="10a22-118">Indifférente</span><span class="sxs-lookup"><span data-stu-id="10a22-118">Any</span></span></p></td>
<td><p><span data-ttu-id="10a22-119">Port de communication serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="10a22-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="10a22-120">Autorise la communication du proxy de serveur Edge XMPP aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="10a22-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10a22-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="10a22-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="10a22-122">Indifférente</span><span class="sxs-lookup"><span data-stu-id="10a22-122">Any</span></span></p></td>
<td><p><span data-ttu-id="10a22-123">Adresse IP de l’interface du serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="10a22-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="10a22-124">Trafic de XMPP interne provenant de la passerelle XMPP du serveur frontal ou du pool frontal sur le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="10a22-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10a22-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10a22-125">See Also</span></span>


[<span data-ttu-id="10a22-126">Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk</span><span class="sxs-lookup"><span data-stu-id="10a22-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="10a22-127">Gestion des partenaires fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10a22-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

