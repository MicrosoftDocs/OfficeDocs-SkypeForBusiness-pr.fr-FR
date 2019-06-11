---
title: 'Lync Server 2013 : Scénarios de proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1621e8bb0241e82f9f4678d4fe39a4f66f6bcf9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="9074a-102">Scénarios de proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9074a-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9074a-103">_**Dernière modification de la rubrique:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="9074a-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="9074a-104">Les proxys inversés sont requis dans Lync Server 2013 pour permettre l’accès aux services et aux ressources tels que la réunion et les URL de connexion, le carnet d’adresses, le contenu de la réunion, le développement de la liste de distribution, les services de mobilité, etc.</span><span class="sxs-lookup"><span data-stu-id="9074a-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="9074a-105">Le scénario classique de proxy inverse dans Lync Server 2013 consiste à autoriser les clients externes (par exemple, le client de bureau ou le client Lync Web App) à accéder au directeur ou aux services Web externes du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="9074a-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="9074a-106">**Proxy inverse et services Web externes**</span><span class="sxs-lookup"><span data-stu-id="9074a-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="9074a-107">![13142405-D5C9-45b7-a8b7-a8c89f09c97c] (images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="9074a-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="9074a-108">Pendant la phase de planification, vous définissez les exigences du proxy inverse dans un déploiement 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9074a-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="9074a-109">Le proxy inverse autorise l’accès à des fonctionnalités pour les clients externes suivants:</span><span class="sxs-lookup"><span data-stu-id="9074a-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="9074a-110">Client de bureau Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9074a-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="9074a-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="9074a-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="9074a-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="9074a-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="9074a-113">application Lync du Windows Store</span><span class="sxs-lookup"><span data-stu-id="9074a-113">Lync Windows Store app</span></span>

<span data-ttu-id="9074a-114">Lors de la planification du déploiement de Lync Server 2013, vous mappez la configuration requise réelle pour Lync Server 2013 aux fonctionnalités de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="9074a-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="9074a-115">Les clients externes se connectent au proxy inverse sur le port TCP 443 et utiliseront SSL (Secure Socket Layer) ou TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="9074a-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="9074a-116">Les clients mobiles Microsoft Lync peuvent se connecter au port TCP 80, mais uniquement lors de l’exécution d’une connexion initiale aux services de découverte de Lync et l’administrateur a configuré les enregistrements de nom de domaine (ou alias) appropriés, et l’accepte la communication ne sera pas chiffrée.</span><span class="sxs-lookup"><span data-stu-id="9074a-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="9074a-117">Les services Web externes de Lync Server 2013 (déployés sur le serveur frontal et/ou le directeur) attendent une connexion d’un proxy inverse sur le port TCP 4443 et il s’attend à ce que la connexion soit SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="9074a-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9074a-118">Les ports d’écoute par défaut suggérés pour les services Web externes sont TCP 8080 pour le trafic HTTP et TCP 4443 pour le trafic HTTPs.</span><span class="sxs-lookup"><span data-stu-id="9074a-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="9074a-119">Le générateur de topologie donne la possibilité de remplacer les valeurs par défaut et de définir vos propres ports d’écoute pour les services Web externes.</span><span class="sxs-lookup"><span data-stu-id="9074a-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="9074a-120">Il est important de noter que le proxy inverse communique avec les services Web externes et que les clients externes communiquent avec le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="9074a-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="9074a-121">Le client externe communique avec le proxy inverse sur le port TCP 443, mais vous pouvez redéfinir le port que le proxy inverse communique avec les services Web externes.</span><span class="sxs-lookup"><span data-stu-id="9074a-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="9074a-122">Les options du générateur de topologie pour remplacer les ports d’écoute par défaut des services Web vous permettent de résoudre les conflits de port d’écoute qui peuvent se produire dans votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="9074a-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="9074a-123">Les services Web externes de Lync Server 2013 attendent un en-tête d’hôte non modifié du client pour identifier le service et l’annuaire du serveur Web que le client tente d’utiliser.</span><span class="sxs-lookup"><span data-stu-id="9074a-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="9074a-124">Les demandes doivent apparaître comme si elles provenaient du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="9074a-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="9074a-125">Les services Web externes utilisent des répertoires virtuels définis par le Web Server (vDir), qui fournissent les services offerts aux clients.</span><span class="sxs-lookup"><span data-stu-id="9074a-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="9074a-126">Les services Web d’identification externes spécifiques sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="9074a-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="9074a-127">VDir pour les réunions de conférences Web</span><span class="sxs-lookup"><span data-stu-id="9074a-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="9074a-128">Le vDir «Dial» pour l’accès téléphonique et la conférence téléphonique</span><span class="sxs-lookup"><span data-stu-id="9074a-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="9074a-129">L’vDir de découverte automatique pour l’application Lync du Windows Store, la version mobile de Lync et le client de bureau Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9074a-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="9074a-130">Le système de découverte automatique de Lync Server 2013 est connu sous le nom DNS «lyncdiscover»</span><span class="sxs-lookup"><span data-stu-id="9074a-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="9074a-131">Les services non définis sont accessibles par le client externe par le biais des appels directs vers les services Web externes.</span><span class="sxs-lookup"><span data-stu-id="9074a-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="9074a-132">Par exemple, l’extension du groupe de distribution (DLX) et le service de carnet d’adresses (ABS) sont accessibles par des appels directs aux services Web externes et des vDirs associés.</span><span class="sxs-lookup"><span data-stu-id="9074a-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="9074a-133">Le client connaît le chemin réel vers vDir et crée un localisateur d’enregistrements uniformes (URL) en fonction de ces informations.</span><span class="sxs-lookup"><span data-stu-id="9074a-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="9074a-134">Le client accède au service de carnet d’adresses à l’aide d’une URL semblable à`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="9074a-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="9074a-135">Serveur Office Web Apps lorsque la Conférence est définie et configurée dans le cadre de la topologie du serveur Lync</span><span class="sxs-lookup"><span data-stu-id="9074a-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9074a-136">Office Web Apps Server est un serveur de rôles distinct et n’est pas configuré dans le cadre des services Web externes.</span><span class="sxs-lookup"><span data-stu-id="9074a-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="9074a-137">Ce serveur est publié séparément pour l’accès client.</span><span class="sxs-lookup"><span data-stu-id="9074a-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="9074a-138">Définissez le pontage SSL pour chaque service.</span><span class="sxs-lookup"><span data-stu-id="9074a-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="9074a-139">Le port externe TCP 443 est mappé au port de services Web externes de TCP 4443.</span><span class="sxs-lookup"><span data-stu-id="9074a-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="9074a-140">Pour le protocole HTTP non chiffré, le port TCP 80 est mappé au port TCP 8080 de port de services Web externes</span><span class="sxs-lookup"><span data-stu-id="9074a-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="9074a-141">Planifier des écouteurs de proxy inversés pour publier des ressources de serveur Web</span><span class="sxs-lookup"><span data-stu-id="9074a-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="9074a-142">Demandez et configurez le certificat de proxy inverse en fonction des services qui seront proposés.</span><span class="sxs-lookup"><span data-stu-id="9074a-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="9074a-143">S’il est configuré avec le nom correct de l’objet, ce certificat peut être partagé par tous les écouteurs configurés du serveur proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="9074a-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="9074a-144">Ressources disponibles pour la planification de votre déploiement de proxy inverse:</span><span class="sxs-lookup"><span data-stu-id="9074a-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="9074a-145">Collecte des données dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9074a-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="9074a-146">Résumé des certificats - Proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9074a-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="9074a-147">Résumé des ports - Proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9074a-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="9074a-148">Résumé DNS - Proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9074a-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

