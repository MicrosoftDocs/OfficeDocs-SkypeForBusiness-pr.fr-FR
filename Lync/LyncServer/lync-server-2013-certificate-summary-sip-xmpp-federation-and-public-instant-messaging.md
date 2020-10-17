---
title: Résumé des certificats-SIP, Fédération XMPP et messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 284a633a2c5ce820009c6672058837bbecb7ecd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517871"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="6c8b0-102">Résumé des certificats-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c8b0-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c8b0-103">_**Dernière modification de la rubrique :** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="6c8b0-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="6c8b0-104">Les certificats dont vous avez besoin pour la Fédération avec Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server seront généralement satisfaits par les certificats que vous configurez, demandez et attribuez à votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6c8b0-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="6c8b0-105">Les certificats requis pour l’activation et l’établissement de communications avec les partenaires XMPP (extensible Messaging and Presence Protocol) nécessitent l’ajout d’entrées pour vos domaines XMPP.</span><span class="sxs-lookup"><span data-stu-id="6c8b0-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="6c8b0-106">L’enregistrement qui est inclus sur le certificat en tant qu’autre nom de l’objet (SAN) est le domaine pouvant participer aux communications XMPP.</span><span class="sxs-lookup"><span data-stu-id="6c8b0-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="6c8b0-107">Ce domaine peut être le domaine de niveau racine (par exemple, contoso.com) si vous voulez activer XMPP pour l’ensemble de votre domaine, ou des domaines enfants sélectionnés (par exemple, corp.contoso.com, finance.contoso.com) si vous activez XMPP pour un sous-ensemble d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6c8b0-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="6c8b0-108">Pour configurer des certificats pour la connectivité de messagerie instantanée publique, Notez qu’il n’y a rien de différent d’autres types de Fédération SIP ou même des certificats de serveur Edge standard, sauf que America Online (AOL) requiert un ou plusieurs certificats (dans le cas d’un pool de serveurs Edge) pour contenir également l’utilisation améliorée de l’étendue client.</span><span class="sxs-lookup"><span data-stu-id="6c8b0-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="6c8b0-109">L’EKU client est un complément du certificat et fait partie du certificat public externe attribué à votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6c8b0-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="6c8b0-110">Pour vérifier que vous avez satisfait aux exigences de certificat appropriées pour votre déploiement de serveur Edge, consultez les rubriques répertoriées dans la section intitulée **Voir aussi**.</span><span class="sxs-lookup"><span data-stu-id="6c8b0-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c8b0-111">Composant</span><span class="sxs-lookup"><span data-stu-id="6c8b0-111">Component</span></span></th>
<th><span data-ttu-id="6c8b0-112">Nom du sujet</span><span class="sxs-lookup"><span data-stu-id="6c8b0-112">Subject name</span></span></th>
<th><span data-ttu-id="6c8b0-113">Autres noms du sujet (SAN)</span><span class="sxs-lookup"><span data-stu-id="6c8b0-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="6c8b0-114">Comments</span><span class="sxs-lookup"><span data-stu-id="6c8b0-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c8b0-115">Serveur Edge externe/d’accès</span><span class="sxs-lookup"><span data-stu-id="6c8b0-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="6c8b0-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c8b0-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6c8b0-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c8b0-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="6c8b0-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c8b0-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="6c8b0-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c8b0-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="6c8b0-120">Pour prendre en charge l’espace de noms XMPP contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c8b0-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="6c8b0-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6c8b0-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="6c8b0-122">Pour prendre en charge l’espace de noms SIP fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6c8b0-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="6c8b0-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6c8b0-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="6c8b0-124">Pour prendre en charge l’espace de noms XMPP fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6c8b0-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="6c8b0-125">Le certificat doit provenir d’une autorité de certification publique et doit disposer de l’utilisation améliorée de l’étendue du serveur et de l’EKU client si la connectivité PIC avec AOL doit être déployée.</span><span class="sxs-lookup"><span data-stu-id="6c8b0-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="6c8b0-126">Le certificat est affecté aux interfaces du serveur Edge externe pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6c8b0-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="6c8b0-127">service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="6c8b0-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="6c8b0-128">service Edge de conférence Web</span><span class="sxs-lookup"><span data-stu-id="6c8b0-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="6c8b0-129">Service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="6c8b0-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="6c8b0-130">Techniquement, un certificat n’est pas affecté au serveur Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="6c8b0-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="6c8b0-131">La communication sécurisée et l’authentification sont gérées par le service d’authentification du serveur relais multimédia (MRAS).</span><span class="sxs-lookup"><span data-stu-id="6c8b0-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="6c8b0-132">MRAS utilise le certificat affecté à l’interface interne du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6c8b0-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="6c8b0-p105">Notez que les autres noms du sujet sont automatiquement ajoutés au certificat en fonction de vos définitions dans le Générateur de topologie. Vous ajoutez des entrées SAN selon les besoins liés aux autres domaines SIP et entrées que vous devez prendre en charge. Le nom du sujet est répliqué dans l’autre nom du sujet et doit être présent pour assurer un fonctionnement correct.</span><span class="sxs-lookup"><span data-stu-id="6c8b0-p105">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c8b0-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6c8b0-136">See Also</span></span>


[<span data-ttu-id="6c8b0-137">Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk</span><span class="sxs-lookup"><span data-stu-id="6c8b0-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="6c8b0-138">Planification des certificats de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c8b0-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="6c8b0-139">Résumé des certificats-serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c8b0-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="6c8b0-140">Résumé des certificats-serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c8b0-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="6c8b0-141">Résumé des certificats-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c8b0-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="6c8b0-142">Résumé des certificats-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c8b0-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="6c8b0-143">Résumé des certificats-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c8b0-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

