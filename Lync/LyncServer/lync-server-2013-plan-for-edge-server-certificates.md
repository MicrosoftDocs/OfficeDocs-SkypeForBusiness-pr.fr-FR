---
title: 'Lync Server 2013 : Planification des certificats de serveur Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faad6dba610df8033b75b0c87c52fbb065dc5dcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="9bb12-102">Planification des certificats de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bb12-102">Plan for Edge Server certificates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bb12-103">_**Dernière modification de la rubrique :** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="9bb12-103">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="9bb12-104">La création de certificats pour Edge est simplifiée dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9bb12-104">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="9bb12-105">**Diagramme de certificats pour le serveur Edge**</span><span class="sxs-lookup"><span data-stu-id="9bb12-105">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="9bb12-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="9bb12-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="9bb12-107">Créez un certificat public unique, assurez-vous d’avoir une clé privée exportable définie pour le certificat et attribuez-la aux interfaces externes du serveur Edge suivantes à l’aide de l’Assistant Certificat :</span><span class="sxs-lookup"><span data-stu-id="9bb12-107">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9bb12-108">Les certificats génériques ne sont pas pris en charge dans Lync Server, sauf s’ils sont utilisés pour résumer les URL simples par le biais du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="9bb12-108">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="9bb12-109">Vous devez définir des noms secondaires d’objet distincts (San) pour chaque nom de domaine SIP, service Edge de conférence Web, service Edge A/V et domaine XMPP offert par votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="9bb12-109">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9bb12-110">Introduite dans Lync Server 2013, les certificats d’authentification audio et vidéo intermédiaires qui avancent l’expiration du certificat actuel nécessitent une planification supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9bb12-110">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="9bb12-111">Au lieu d’utiliser un certificat à des fins différentes pour l’interface de bord externe, vous devez disposer de deux certificats, l’un attribué au service Edge d’accès et au service Edge de conférence Web, et un certificat pour le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="9bb12-111">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="9bb12-112">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Configuration des certificats d’audiovisuel et des certificats OAuth dans Lync Server 2013 avec l’application Set-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="9bb12-112">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9bb12-113">Dans le cas d’un pool de serveurs Edge, vous exportez le certificat avec la clé privée vers chaque serveur Edge et vous attribuez le certificat à chaque service Edge Server.</span><span class="sxs-lookup"><span data-stu-id="9bb12-113">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="9bb12-114">Procédez de la même façon pour le certificat de serveur Edge interne, en exportant le certificat avec la clé privée et en l’affectant à chaque interface de bord interne.</span><span class="sxs-lookup"><span data-stu-id="9bb12-114">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="9bb12-115">Vérifiez que vous avez affecté une clé privée exportée au certificat.</span><span class="sxs-lookup"><span data-stu-id="9bb12-115">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="9bb12-116">Service Edge d’accès (appelé **Edge d’accès SIP externe** dans l’Assistant certificat)</span><span class="sxs-lookup"><span data-stu-id="9bb12-116">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="9bb12-117">Service Edge de conférence Web (connu sous le nom de **conférence Web externe** dans l’Assistant certificat)</span><span class="sxs-lookup"><span data-stu-id="9bb12-117">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="9bb12-118">Service d’authentification a/V (appelé par le biais de l' **extérieur** de l’Assistant certificat)</span><span class="sxs-lookup"><span data-stu-id="9bb12-118">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="9bb12-119">Créez un certificat interne unique avec une clé privée exportable, puis copiez-le et attribuez-le à chaque interface interne du serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="9bb12-119">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="9bb12-120">Serveur Edge (appelé **Edge Internal** dans l’Assistant certificat)</span><span class="sxs-lookup"><span data-stu-id="9bb12-120">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9bb12-121">Il est possible d’utiliser des certificats distincts et distincts pour chaque service Edge Server.</span><span class="sxs-lookup"><span data-stu-id="9bb12-121">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="9bb12-122">Il peut s’avérer utile de choisir des certificats séparés si vous souhaitez utiliser la nouvelle fonctionnalité de certificat de déploiement pour le certificat de service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="9bb12-122">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="9bb12-123">Dans le cas de cette fonctionnalité, il est recommandé de découpler le certificat de service Edge A/V du service Edge d’accès et du service Edge de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="9bb12-123">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="9bb12-124">Si vous choisissez de demander, d’acquérir et d’affecter des certificats séparés pour chaque service, vous devez demander à la clé privée d’être exportable pour le service Edge A/v (de nouveau, il s’agit de la fonction de service d’authentification A/v) et de lui attribuer le même certificat sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="9bb12-124">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9bb12-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9bb12-125">See Also</span></span>


[<span data-ttu-id="9bb12-126">Test de l’audiovisuel et des certificats OAuth dans Lync Server 2013 à l’aide du CsCertificate</span><span class="sxs-lookup"><span data-stu-id="9bb12-126">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="9bb12-127">Modifications apportées dans Lync Server 2013 affectant la planification de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="9bb12-127">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

