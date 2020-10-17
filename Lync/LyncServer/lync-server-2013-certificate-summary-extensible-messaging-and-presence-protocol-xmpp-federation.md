---
title: 'Lync Server 2013 : Résumé des certificats-Fédération XMPP (extensible Messaging and Presence Protocol)'
description: 'Lync Server 2013 : Résumé des certificats-Fédération XMPP (extensible Messaging and Presence Protocol).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e2bb593d909c2eec6032dc89c07cc5f5b1a72db
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572340"
---
# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="181ea-103">Résumé des certificats-Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="181ea-103">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="181ea-104">_**Dernière modification de la rubrique :** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="181ea-104">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="181ea-p101">Les exigences de certificat pour l’activation et l’établissement de communications avec des partenaires XMPP (Extensible Messaging and Presence Protocol) requièrent l’enregistrement supplémentaire de vos domaines XMPP. L’enregistrement qui est inclus sur le certificat en tant qu’autre nom de l’objet (SAN) est le domaine pouvant participer aux communications XMPP. Ce domaine peut être le domaine de niveau racine (par exemple, contoso.com) si vous voulez activer XMPP pour l’ensemble de votre domaine, ou des domaines enfants sélectionnés (par exemple, corp.contoso.com, finance.contoso.com) si vous activez XMPP pour un sous-ensemble d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="181ea-p101">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains. The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications. The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="181ea-108">Résumé du certificat pour le protocole XMPP</span><span class="sxs-lookup"><span data-stu-id="181ea-108">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="181ea-109">Composant</span><span class="sxs-lookup"><span data-stu-id="181ea-109">Component</span></span></th>
<th><span data-ttu-id="181ea-110">Nom du sujet</span><span class="sxs-lookup"><span data-stu-id="181ea-110">Subject name</span></span></th>
<th><span data-ttu-id="181ea-111">Autres noms du sujet (SAN)/Ordre</span><span class="sxs-lookup"><span data-stu-id="181ea-111">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="181ea-112">Comments</span><span class="sxs-lookup"><span data-stu-id="181ea-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="181ea-113">Attribuer au service Edge d’accès d’un serveur Edge ou d’un pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="181ea-113">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="181ea-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="181ea-114">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="181ea-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="181ea-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="181ea-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="181ea-116">sip.contoso.com</span></span></p>
<p><span data-ttu-id="181ea-117">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="181ea-117">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="181ea-118">contoso.com</span><span class="sxs-lookup"><span data-stu-id="181ea-118">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="181ea-119">Les trois premières entrées SAN sont les entrées SAN normales pour un serveur Edge complet.</span><span class="sxs-lookup"><span data-stu-id="181ea-119">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="181ea-120">L’entrée contoso.com correspond à l’entrée requise pour la fédération avec le partenaire XMPP au niveau du domaine racine.</span><span class="sxs-lookup"><span data-stu-id="181ea-120">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="181ea-121">Cette entrée autorisera XMPP pour tous les domaines dont le suffixe est contoso.com.</span><span class="sxs-lookup"><span data-stu-id="181ea-121">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="181ea-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="181ea-122">See Also</span></span>


[<span data-ttu-id="181ea-123">Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk</span><span class="sxs-lookup"><span data-stu-id="181ea-123">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="181ea-124">Planification des certificats de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="181ea-124">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="181ea-125">Configurer des certificats de serveur Edge pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="181ea-125">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="181ea-126">Request-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="181ea-126">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="181ea-127">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="181ea-127">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

