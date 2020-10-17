---
title: 'Lync Server 2013 : Résumé des certificats-connectivité de messagerie instantanée publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdc4bba8064332d7fa3f90d0d6a3d4b9f6cef9e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512781"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="b1d2d-102">Résumé des certificats-connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1d2d-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1d2d-103">_**Dernière modification de la rubrique :** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="b1d2d-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="b1d2d-104">Pour configurer des certificats pour la connectivité de messagerie instantanée publique, vous devez tout d’abord remarquer qu’il n’y a rien de différent des autres types de Fédération SIP ou même des certificats de serveur Edge standard, à la seule différence qu’America Online (AOL) nécessite une configuration de certificat unique.</span><span class="sxs-lookup"><span data-stu-id="b1d2d-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="b1d2d-105">En plus de l’utilisation avancée de la clé (EKU) du serveur, America Online nécessite le certificat ou les certificats (dans le cas d’un pool de serveurs Edge) pour contenir également l’utilisation améliorée de la clé client.</span><span class="sxs-lookup"><span data-stu-id="b1d2d-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="b1d2d-106">L’EKU client est un complément du certificat et fait partie du certificat public externe attribué à votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b1d2d-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b1d2d-107">Résumé du certificat – Connectivité PIC (Public IM Connectivity)</span><span class="sxs-lookup"><span data-stu-id="b1d2d-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1d2d-108">Composant</span><span class="sxs-lookup"><span data-stu-id="b1d2d-108">Component</span></span></th>
<th><span data-ttu-id="b1d2d-109">Nom du sujet</span><span class="sxs-lookup"><span data-stu-id="b1d2d-109">Subject name</span></span></th>
<th><span data-ttu-id="b1d2d-110">Autres noms du sujet (SAN)/Ordre</span><span class="sxs-lookup"><span data-stu-id="b1d2d-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="b1d2d-111">Comments</span><span class="sxs-lookup"><span data-stu-id="b1d2d-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1d2d-112">Serveur Edge externe/d’accès</span><span class="sxs-lookup"><span data-stu-id="b1d2d-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="b1d2d-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b1d2d-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b1d2d-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b1d2d-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="b1d2d-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b1d2d-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="b1d2d-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1d2d-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="b1d2d-117">Le certificat doit provenir d’une autorité de certification publique et doit disposer de l’utilisation améliorée de l’étendue du serveur et de l’EKU client si la connectivité PIC avec AOL doit être déployée.</span><span class="sxs-lookup"><span data-stu-id="b1d2d-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="b1d2d-118">Le certificat est affecté aux interfaces du serveur Edge externe pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b1d2d-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="b1d2d-119">service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="b1d2d-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="b1d2d-120">service Edge de conférence Web</span><span class="sxs-lookup"><span data-stu-id="b1d2d-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="b1d2d-121">Service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="b1d2d-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="b1d2d-p103">Notez que les autres noms du sujet sont automatiquement ajoutés au certificat en fonction de vos définitions dans le Générateur de topologie. Vous ajoutez des entrées SAN selon les besoins liés aux autres domaines SIP et entrées que vous devez prendre en charge. Le nom du sujet est répliqué dans l’autre nom du sujet et doit être présent pour assurer un fonctionnement correct.</span><span class="sxs-lookup"><span data-stu-id="b1d2d-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1d2d-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1d2d-125">See Also</span></span>


[<span data-ttu-id="b1d2d-126">Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1d2d-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

