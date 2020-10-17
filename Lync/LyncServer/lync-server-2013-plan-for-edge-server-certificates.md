---
title: 'Lync Server 2013 : planification des certificats de serveur Edge'
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
ms.openlocfilehash: a3fc6ab9bfb6d145b324c079e4bf746354e7329f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519851"
---
# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="6cad7-102">Planification des certificats de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cad7-102">Plan for Edge Server certificates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cad7-103">_**Dernière modification de la rubrique :** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="6cad7-103">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="6cad7-104">La création de certificats pour Edge est simplifiée dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6cad7-104">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="6cad7-105">**Organigramme des certificats pour le serveur Edge**</span><span class="sxs-lookup"><span data-stu-id="6cad7-105">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="6cad7-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="6cad7-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="6cad7-107">Créez un seul certificat public, vérifiez que vous disposez d’une clé privée exportable définie pour le certificat, et affectez-la aux interfaces externes du serveur Edge suivantes à l’aide de l’Assistant Certificat :</span><span class="sxs-lookup"><span data-stu-id="6cad7-107">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6cad7-108">Les certificats génériques ne sont pas pris en charge dans Lync Server, sauf s’ils sont utilisés pour résumer les URL simples via le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="6cad7-108">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="6cad7-109">Vous devez définir des noms d’autres objets distincts (San) pour chaque nom de domaine SIP, service Edge de conférence Web, service Edge A/V et domaine XMPP offert par votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="6cad7-109">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="6cad7-110">Introduit dans Lync Server 2013, la mise en place de certificats d’authentification audio/vidéo avant le délai d’expiration du certificat actuel nécessite une planification supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="6cad7-110">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="6cad7-111">Au lieu d’un certificat à plusieurs fins pour l’interface Edge externe, vous aurez besoin de deux certificats, un affecté au service Edge d’accès et au service Edge de conférence Web, et un certificat pour le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="6cad7-111">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="6cad7-112">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth Certificates in Lync Server 2013 using-rouleaux in set-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="6cad7-112">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6cad7-113">Dans le cas d’un pool de serveurs Edge, vous exportez le certificat avec la clé privée vers chaque serveur Edge et vous affectez le certificat à chaque service serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6cad7-113">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="6cad7-114">Procédez de la même manière pour le certificat de serveur Edge interne, en exportant le certificat avec la clé privée et en l’affectant à chaque interface Edge interne.</span><span class="sxs-lookup"><span data-stu-id="6cad7-114">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="6cad7-115">Assurez-vous qu’une clé privée exportable est attribuée au certificat.</span><span class="sxs-lookup"><span data-stu-id="6cad7-115">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="6cad7-116">Service Edge d’accès (appelé serveur **Edge d’accès SIP externe** dans l’Assistant certificat)</span><span class="sxs-lookup"><span data-stu-id="6cad7-116">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="6cad7-117">Service Edge de conférence Web (appelé serveur **Edge de conférence Web externe** dans l’Assistant certificat)</span><span class="sxs-lookup"><span data-stu-id="6cad7-117">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="6cad7-118">Service d’authentification a/V (appelé serveur **Edge a/v externe** dans l’Assistant certificat)</span><span class="sxs-lookup"><span data-stu-id="6cad7-118">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="6cad7-119">Créez un certificat interne unique avec une clé privée exportable, copiez-le et affectez-le à chacune des interfaces internes du serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="6cad7-119">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="6cad7-120">Serveur Edge (appelé serveur Edge **interne** dans l’Assistant certificat)</span><span class="sxs-lookup"><span data-stu-id="6cad7-120">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6cad7-121">Il est possible d’utiliser des certificats distincts et distincts pour chaque service serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6cad7-121">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="6cad7-122">Si vous souhaitez utiliser la nouvelle fonctionnalité de certificat de déploiement pour le certificat de service Edge A/V, il est recommandé de choisir des certificats distincts.</span><span class="sxs-lookup"><span data-stu-id="6cad7-122">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="6cad7-123">Dans le cas de cette fonctionnalité, nous vous recommandons de découpler le certificat de service Edge A/V du service Edge d’accès et du service Edge de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="6cad7-123">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="6cad7-124">Si vous choisissez de demander, d’acquérir et d’affecter des certificats distincts pour chaque service, vous devez demander à ce que la clé privée soit exportable pour le service Edge A/V (là encore, il s’agit du service d’authentification A/V) et affectez le même certificat à l’interface externe Edge A/V sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="6cad7-124">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6cad7-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6cad7-125">See Also</span></span>


[<span data-ttu-id="6cad7-126">Staging des certificats AV et OAuth dans Lync Server 2013 avec l’utilisation de la CsCertificate</span><span class="sxs-lookup"><span data-stu-id="6cad7-126">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="6cad7-127">Modifications apportées dans Lync Server 2013 affectant la planification des serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="6cad7-127">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

