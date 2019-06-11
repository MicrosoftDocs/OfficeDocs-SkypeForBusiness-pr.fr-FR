---
title: Résumé du certificat-SIP, Fédération de XMPP et messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dccb46b9f2b6d934f1cd0960bb11a369fb585ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="6940c-102">Résumé du certificat-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6940c-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6940c-103">_**Dernière modification de la rubrique:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="6940c-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="6940c-104">Les certificats dont vous avez besoin pour la Fédération avec Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server seront généralement satisfaits par les certificats que vous configurez, demandez et attribuez à votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6940c-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="6940c-105">Les exigences en matière de certificats pour l’activation et la définition des communications avec les partenaires de messagerie et de présence (en anglais) en fonction du protocole de messagerie extensible nécessitent l’ajout d’entrées pour vos domaines XMPP.</span><span class="sxs-lookup"><span data-stu-id="6940c-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="6940c-106">L’enregistrement figurant sur le certificat en tant que autre nom de l’objet (SAN) sera le domaine qui peut participer aux communications XMPP.</span><span class="sxs-lookup"><span data-stu-id="6940c-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="6940c-107">Le domaine peut être le domaine de niveau racine (par exemple, contoso.com) si vous souhaitez activer la XMPP pour l’ensemble de votre domaine ou si vous pouvez sélectionner des domaines enfants (par exemple, corp.contoso.com, finance.contoso.com) si vous activez XMPP pour un sous-ensemble d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6940c-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="6940c-108">Pour configurer des certificats pour la connectivité de messagerie instantanée publique, Notez qu’il n’y a rien d’autre que d’autres types de Fédération SIP ou même des certificats de serveur Edge standard, à l’exception que America Online (AOL) nécessite le ou les certificats (en dans le cas d’un pool de bords, le cas échéant, il s’agit de l’utilisation de l’utilisation améliorée du client.</span><span class="sxs-lookup"><span data-stu-id="6940c-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="6940c-109">L’utilisation améliorée de l’utilisation du client est un ajout du certificat, qui fait partie du certificat public externe affecté à votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6940c-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="6940c-110">Pour vérifier que vous remplissez les conditions requises pour les certificats pour le déploiement de Microsoft Edge Server, reportez-vous aux rubriques indiquées dans la section **Voir aussi**.</span><span class="sxs-lookup"><span data-stu-id="6940c-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

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
<th><span data-ttu-id="6940c-111">Composant</span><span class="sxs-lookup"><span data-stu-id="6940c-111">Component</span></span></th>
<th><span data-ttu-id="6940c-112">Nom de l’objet</span><span class="sxs-lookup"><span data-stu-id="6940c-112">Subject name</span></span></th>
<th><span data-ttu-id="6940c-113">Autres noms d’objet (SAN)</span><span class="sxs-lookup"><span data-stu-id="6940c-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="6940c-114">Commentaires</span><span class="sxs-lookup"><span data-stu-id="6940c-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6940c-115">Périphérie externe/accès</span><span class="sxs-lookup"><span data-stu-id="6940c-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="6940c-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6940c-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6940c-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6940c-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="6940c-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6940c-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="6940c-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="6940c-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="6940c-120">Pour prendre en charge l’espace de noms contoso.com XMPP</span><span class="sxs-lookup"><span data-stu-id="6940c-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="6940c-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6940c-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="6940c-122">Pour prendre en charge l’espace de noms SIP fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6940c-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="6940c-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6940c-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="6940c-124">Pour prendre en charge l’espace de noms fabrikam.com XMPP</span><span class="sxs-lookup"><span data-stu-id="6940c-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="6940c-125">Le certificat doit faire partir d’une autorité de certification publique et doit disposer de l’utilisation de l’utilisation améliorée de l’utilisation du serveur et de l’utilisation améliorée de la messagerie instantanée pour le client.</span><span class="sxs-lookup"><span data-stu-id="6940c-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="6940c-126">Le certificat est attribué aux interfaces du serveur Edge externe pour les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="6940c-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="6940c-127">Service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="6940c-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="6940c-128">Service Edge de conférence web</span><span class="sxs-lookup"><span data-stu-id="6940c-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="6940c-129">Service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="6940c-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="6940c-130">Techniquement, un certificat n’est pas affecté au bord A/V.</span><span class="sxs-lookup"><span data-stu-id="6940c-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="6940c-131">La communication et l’authentification sécurisées sont gérées par le biais du service d’authentification par relais de média (MRAS).</span><span class="sxs-lookup"><span data-stu-id="6940c-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="6940c-132">MRAS utilise le certificat attribué à l’interface interne du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6940c-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="6940c-133">Notez que les San sont automatiquement ajoutés au certificat en fonction de vos définitions dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="6940c-133">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="6940c-134">Vous pouvez ajouter des entrées SAN selon vos besoins pour des domaines SIP supplémentaires et d’autres entrées que vous devez prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="6940c-134">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="6940c-135">Le nom du sujet est répliqué sur le SAN et doit être présent pour une opération correcte.</span><span class="sxs-lookup"><span data-stu-id="6940c-135">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6940c-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6940c-136">See Also</span></span>


[<span data-ttu-id="6940c-137">Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk</span><span class="sxs-lookup"><span data-stu-id="6940c-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="6940c-138">Planification des certificats de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6940c-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="6940c-139">Résumé des certificats - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6940c-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="6940c-140">Résumé des certificats - Serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6940c-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="6940c-141">Résumé des certificats - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6940c-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="6940c-142">Résumé des certificats - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6940c-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="6940c-143">Résumé des certificats - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6940c-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

