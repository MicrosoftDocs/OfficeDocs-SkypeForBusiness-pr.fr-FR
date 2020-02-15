---
title: 'Lync Server 2013 : configuration requise pour le proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efa0124bb66974755a7cae0ab799dc66cc48fd1e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="2ddc2-102">Configuration requise pour le proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ddc2-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ddc2-103">_**Dernière modification de la rubrique :** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="2ddc2-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="2ddc2-104">Lync Server 2013 impose quelques exigences sur les communications à partir du client externe, qui sont ensuite transmises aux services Web externes hébergés sur le directeur, le pool Directeur, le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="2ddc2-105">Le proxy inverse est également responsable de la publication d’Office Web Apps Server, si vous proposez des conférences à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2ddc2-106">Lync Server 2013 ne spécifie pas un proxy inverse particulier que vous devez utiliser.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="2ddc2-107">Lync Server 2013 définit uniquement les exigences opérationnelles que le proxy inverse doit être en mesure de faire.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="2ddc2-108">En règle générale, le proxy inverse que vous avez déjà déployé dans votre infrastructure peut répondre aux exigences.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="2ddc2-109">Exigences relatives au proxy inverse</span><span class="sxs-lookup"><span data-stu-id="2ddc2-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="2ddc2-110">Les opérations fonctionnelles que Lync Server 2013 attend qu’un proxy inverse effectuent sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ddc2-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="2ddc2-111">Utilisez les protocoles SSL (Secure Socket Layer) et TLS (Transport Layer Security) implémentés à l’aide de certificats acquis auprès d’une autorité de certification publique pour se connecter aux services Web externes publiés du directeur, du pool Directeur, du serveur frontal ou du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="2ddc2-112">Le directeur et le serveur frontal peuvent se trouver dans un pool à charge équilibrée à l’aide d’programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="2ddc2-113">En mesure de publier des sites Web internes à l’aide de certificats pour le chiffrement, ou de les publier sur des moyens non chiffrés, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="2ddc2-114">En mesure de publier un site Web hébergé en interne de façon externe à l’aide d’un nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="2ddc2-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="2ddc2-115">En mesure de publier tout le contenu du site Web hébergé.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="2ddc2-116">Par défaut, vous pouvez utiliser la \*\* / \*\* directive, qui est reconnue par la plupart des serveurs Web comme signifiant « publier tout le contenu sur le serveur Web ».</span><span class="sxs-lookup"><span data-stu-id="2ddc2-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="2ddc2-117">Vous pouvez également modifier la directive (par exemple, **/Uwca/\***, ce qui signifie « publier tout le contenu sous le répertoire virtuel Ucwa ».</span><span class="sxs-lookup"><span data-stu-id="2ddc2-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="2ddc2-118">Doit être configurable pour exiger des connexions SSL (Secure Sockets Layer) et/ou TLS (Transport Layer Security) avec des clients qui demandent du contenu à partir d’un site Web publié.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="2ddc2-119">Doit accepter les certificats avec des entrées de l’autre nom de l’objet (SAN).</span><span class="sxs-lookup"><span data-stu-id="2ddc2-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="2ddc2-120">Doit pouvoir autoriser la liaison d’un certificat à un écouteur ou une interface par le biais duquel le nom de domaine complet des services Web externes est résolu.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="2ddc2-121">Les configurations de l’écouteur sont préférables aux interfaces.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="2ddc2-122">De nombreux écouteurs peuvent être configurés sur une seule interface.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="2ddc2-123">Doit autoriser la configuration de la gestion des en-têtes d’hôte.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="2ddc2-124">Souvent, l’en-tête d’hôte d’origine envoyé par le client demandeur doit être passé de manière transparente, au lieu d’être modifié par le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="2ddc2-125">Le pontage du trafic SSL et TLS à partir d’un port défini de manière externe (par exemple, TCP 443) vers un autre port défini (par exemple, TCP 4443).</span><span class="sxs-lookup"><span data-stu-id="2ddc2-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="2ddc2-126">Le proxy inverse peut déchiffrer le paquet lors de sa réception, puis rechiffrer le paquet lors de l’envoi.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="2ddc2-127">Le pontage du trafic TCP non chiffré à partir d’un port (par exemple, TCP 80) vers un autre (par exemple, TCP 8080).</span><span class="sxs-lookup"><span data-stu-id="2ddc2-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="2ddc2-128">Autorisez la configuration ou acceptez, l’authentification NTLM, aucune authentification et authentification directe.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

