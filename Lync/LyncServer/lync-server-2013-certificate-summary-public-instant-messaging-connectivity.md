---
title: 'Lync Server 2013: Résumé de certification-connectivité de messagerie instantanée publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31988207403ef1ccb5ea366da6e1ec6b3d448b4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="e9e9e-102">Résumé de certification-connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9e9e-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9e9e-103">_**Dernière modification de la rubrique:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="e9e9e-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="e9e9e-104">Pour configurer des certificats pour la connectivité de messagerie instantanée publique, vous devez d’abord noter qu’il n’y a rien d’autre que d’autres types de Fédération SIP ou même des certificats de serveur Edge standard, à l’exception que America Online (AOL) nécessite une seule configuration de certificat.</span><span class="sxs-lookup"><span data-stu-id="e9e9e-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="e9e9e-105">Outre l’utilisation améliorée de la clé avancée du serveur, America Online nécessite que le ou les certificats (dans le cas d’un pool de périphérie) contiennent également l’utilisation améliorée de l’utilisation du client.</span><span class="sxs-lookup"><span data-stu-id="e9e9e-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="e9e9e-106">L’utilisation améliorée de l’utilisation du client est un ajout du certificat, qui fait partie du certificat public externe affecté à votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="e9e9e-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="e9e9e-107">Résumé de certification-connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="e9e9e-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9e9e-108">Composant</span><span class="sxs-lookup"><span data-stu-id="e9e9e-108">Component</span></span></th>
<th><span data-ttu-id="e9e9e-109">Nom de l’objet</span><span class="sxs-lookup"><span data-stu-id="e9e9e-109">Subject name</span></span></th>
<th><span data-ttu-id="e9e9e-110">Autres noms d’objet (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="e9e9e-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="e9e9e-111">Commentaires</span><span class="sxs-lookup"><span data-stu-id="e9e9e-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9e9e-112">Périphérie externe/accès</span><span class="sxs-lookup"><span data-stu-id="e9e9e-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="e9e9e-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e9e9e-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e9e9e-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e9e9e-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="e9e9e-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e9e9e-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="e9e9e-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="e9e9e-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="e9e9e-117">Le certificat doit faire partir d’une autorité de certification publique et doit disposer de l’utilisation de l’utilisation améliorée de l’utilisation du serveur et de l’utilisation améliorée de la messagerie instantanée pour le client.</span><span class="sxs-lookup"><span data-stu-id="e9e9e-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="e9e9e-118">Le certificat est attribué aux interfaces du serveur Edge externe pour les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="e9e9e-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="e9e9e-119">Service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="e9e9e-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="e9e9e-120">Service Edge de conférence web</span><span class="sxs-lookup"><span data-stu-id="e9e9e-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="e9e9e-121">Service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="e9e9e-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="e9e9e-122">Notez que les San sont automatiquement ajoutés au certificat en fonction de vos définitions dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="e9e9e-122">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="e9e9e-123">Vous pouvez ajouter des entrées SAN selon vos besoins pour des domaines SIP supplémentaires et d’autres entrées que vous devez prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="e9e9e-123">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="e9e9e-124">Le nom du sujet est répliqué sur le SAN et doit être présent pour une opération correcte.</span><span class="sxs-lookup"><span data-stu-id="e9e9e-124">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e9e9e-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e9e9e-125">See Also</span></span>


[<span data-ttu-id="e9e9e-126">Scénarios d’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9e9e-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

