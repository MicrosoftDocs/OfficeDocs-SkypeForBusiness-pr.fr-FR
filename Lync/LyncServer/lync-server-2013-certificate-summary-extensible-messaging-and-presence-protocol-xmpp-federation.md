---
title: 'Lync Server 2013 : Résumé de certification-Fédération de protocoles de messagerie extensible et de présence'
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
ms.openlocfilehash: 7af2c226397c5225fc26f6dbdf40d12a4bdb1ca0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="43d27-102">Résumé de certification-Fédération de protocoles de messagerie extensible et de présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43d27-102">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43d27-103">_**Dernière modification de la rubrique :** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="43d27-103">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="43d27-104">Les exigences en matière de certificats pour l’activation et la définition des communications avec les partenaires de messagerie électronique et de présence (XMPP) requièrent l’enregistrement supplémentaire de vos domaines XMPP.</span><span class="sxs-lookup"><span data-stu-id="43d27-104">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains.</span></span> <span data-ttu-id="43d27-105">L’enregistrement figurant sur le certificat en tant que autre nom de l’objet (SAN) sera le domaine qui peut participer aux communications XMPP.</span><span class="sxs-lookup"><span data-stu-id="43d27-105">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="43d27-106">Le domaine peut être le domaine de niveau racine (par exemple, contoso.com) si vous souhaitez activer la XMPP pour l’ensemble de votre domaine ou si vous pouvez sélectionner des domaines enfants (par exemple, corp.contoso.com, finance.contoso.com) si vous activez XMPP pour un sous-ensemble d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="43d27-106">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="43d27-107">Résumé du certificat pour le protocole extensible de messagerie et de présence</span><span class="sxs-lookup"><span data-stu-id="43d27-107">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43d27-108">Composant</span><span class="sxs-lookup"><span data-stu-id="43d27-108">Component</span></span></th>
<th><span data-ttu-id="43d27-109">Nom de l’objet</span><span class="sxs-lookup"><span data-stu-id="43d27-109">Subject name</span></span></th>
<th><span data-ttu-id="43d27-110">Autres noms d’objet (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="43d27-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="43d27-111">Commentaires</span><span class="sxs-lookup"><span data-stu-id="43d27-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43d27-112">Affecter au service Edge d’accès du serveur Edge ou du pool de périphérie</span><span class="sxs-lookup"><span data-stu-id="43d27-112">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="43d27-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="43d27-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="43d27-114">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="43d27-114">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="43d27-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="43d27-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="43d27-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="43d27-116">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="43d27-117">contoso.com</span><span class="sxs-lookup"><span data-stu-id="43d27-117">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="43d27-118">Les trois premières entrées du SAN sont les entrées SAN normales pour un serveur de périphérie complet.</span><span class="sxs-lookup"><span data-stu-id="43d27-118">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="43d27-119">Contoso.com est l’entrée requise pour la Fédération avec le partenaire XMPP au niveau du domaine racine.</span><span class="sxs-lookup"><span data-stu-id="43d27-119">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="43d27-120">Cette entrée autorise la fonction XMPP pour tous les domaines dont le suffixe est contoso.com.</span><span class="sxs-lookup"><span data-stu-id="43d27-120">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="43d27-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43d27-121">See Also</span></span>


[<span data-ttu-id="43d27-122">Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk</span><span class="sxs-lookup"><span data-stu-id="43d27-122">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="43d27-123">Planification des certificats de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43d27-123">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="43d27-124">Configuration des certificats de serveur Edge pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43d27-124">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="43d27-125">Requête-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="43d27-125">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="43d27-126">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="43d27-126">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

