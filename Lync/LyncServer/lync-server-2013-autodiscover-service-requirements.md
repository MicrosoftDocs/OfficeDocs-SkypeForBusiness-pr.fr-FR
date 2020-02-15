---
title: 'Lync Server 2013 : configuration requise pour le service de découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cb27cb95e14a811dd6fc33bf8af91d51c26172
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="b4d9a-102">Configuration requise pour le service de découverte automatique pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4d9a-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4d9a-103">_**Dernière modification de la rubrique :** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="b4d9a-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="b4d9a-104">Le service de découverte automatique Microsoft Lync Server 2013 s’exécute sur les serveurs directeur et de pool frontal, et lorsqu’il est publié dans le système DNS, peut être utilisé par les appareils mobiles exécutant Lync mobile pour localiser les services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="b4d9a-105">Avant que les appareils mobiles exécutant Lync mobile puissent tirer parti de la découverte automatique, vous devez modifier les listes des autres noms de sujet du certificat sur un directeur et un serveur frontal exécutant le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="b4d9a-106">En outre, il peut s’avérer nécessaire de modifier les listes des autres noms de sujet sur les certificats utilisés pour les règles de publication des services web externes sur les proxys inverses.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="b4d9a-107">Pour plus d’informations sur les entrées des autres noms de sujet requises pour les directeurs, les serveurs frontaux et les proxys inverses, voir [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) dans Planning for Mobility.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="b4d9a-108">La décision d’utiliser des listes d’autres noms de sujet sur les proxys inverses repose sur votre choix de publier le service de découverte automatique sur le port 80 ou sur le port 443 :</span><span class="sxs-lookup"><span data-stu-id="b4d9a-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="b4d9a-109">**Publié sur le port 80**   aucune modification de certificat n’est requise si la requête initiale du service de découverte automatique a lieu sur le port 80.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="b4d9a-110">Cela est dû au fait que les appareils mobiles exécutant Lync accèdent au proxy inverse sur le port 80 de manière externe, puis sont redirigés vers un directeur ou un serveur frontal sur le port 8080 en interne.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="b4d9a-111">Pour plus d’informations, consultez la section « Processus de découverte automatique initiale à l’aide du port 80 » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="b4d9a-112">**Publié sur le port 443**   la liste autre nom du sujet sur les certificats utilisés par la règle de publication des services Web externes doit contenir un *lyncdiscover.\< entrée\> sipdomain* pour chaque domaine SIP au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="b4d9a-113">La réémission de certificats à l’aide d’une autorité de certification interne constitue généralement un processus simple, mais pour les certificats publics utilisés dans la règle de publication des services web, l’ajout de plusieurs entrées d’autres noms de sujet peut s’avérer onéreux.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="b4d9a-114">Pour contourner ce problème, nous prenons en charge la connexion de découverte automatique initiale via le port 80, qui est ensuite redirigé vers le port 8080 sur le directeur ou le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="b4d9a-115">Par exemple, supposons qu’un client mobile exécutant Lync mobile est configuré pour se connecter à Lync Server 2013 à l’aide de la fonctionnalité de découverte automatique à l’aide du protocole HTTP pour la demande initiale.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="b4d9a-116">Processus de découverte automatique initiale pour les appareils mobiles utilisant le port 80</span><span class="sxs-lookup"><span data-stu-id="b4d9a-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="b4d9a-117">Appareil mobile exécutant Lync mobile recherche lyncdiscover.contoso.com à l’aide de DNS, où se trouve un enregistrement A.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="b4d9a-118">DNS externe renvoie l’adresse IP pour les services Web externes au client.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="b4d9a-119">L’appareil mobile exécutant Lync mobile envoie http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com une demande au proxy inverse</span><span class="sxs-lookup"><span data-stu-id="b4d9a-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="b4d9a-120">La règle de publication Web va relier la demande du port 80 de manière externe au port 8080 en interne, qui l’acheminera vers un directeur ou un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="b4d9a-121">Étant donné qu’il s’agit d’une requête HTTP et non HTTPS, aucune modification n’est requise dans le certificat stipulé dans la règle de publication des services web externes afin de prendre en charge le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="b4d9a-122">Le service de découverte automatique renvoie les URL des services web externes (au format HTTPS).</span><span class="sxs-lookup"><span data-stu-id="b4d9a-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="b4d9a-123">L’appareil mobile exécutant Lync mobile peut alors se reconnecter au proxy inverse sur le port 443 et être redirigé sur 4443 vers le service de mobilité s’exécutant sur le pool d’accueil de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="b4d9a-124">Étant donné que la requête HTTPS concerne l’URL des services web externes par rapport à l’URL du service de découverte automatique, elle réussit car le certificat doit déjà contenir les entrées des autres noms de sujet pour les noms de domaine complets (FQDN) des services web externes.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="b4d9a-125">Dans ce scénario, aucune modification de certificat n’est requise pour prendre en charge la mobilité.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4d9a-126">Si le serveur web cible possède un certificat qui ne dispose pas d’une adresse correspondant à lyncdiscover.contoso.com en tant que valeur de la liste des autres noms de sujet :</span><span class="sxs-lookup"><span data-stu-id="b4d9a-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="b4d9a-127">un serveur&nbsp;&nbsp;&nbsp;. Web répond avec un « Server Hello » et aucun certificat.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="b4d9a-128">b.&nbsp;&nbsp;&nbsp;l’appareil mobile exécutant Lync mobile met immédiatement fin à la session.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="b4d9a-129">Si le serveur web cible possède un certificat qui comprend lyncdiscover.contoso.com comme valeur de la liste des autres noms de sujet :</span><span class="sxs-lookup"><span data-stu-id="b4d9a-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="b4d9a-130">un serveur&nbsp;&nbsp;&nbsp;. Web répond avec un « serveur Hello » et un certificat.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="b4d9a-131">b.&nbsp;&nbsp;&nbsp;l’appareil mobile exécutant Lync mobile valide le certificat et termine le protocole de transfert.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="b4d9a-132">Pour prendre en charge une connexion initiale au service de découverte automatique utilisant le port 80 sur votre serveur proxy inverse, vous pouvez créer une règle de publication http similaire à cet exemple pour une règle de publication web de proxy inverse Forefront Threat Management Gateway 2010 :</span><span class="sxs-lookup"><span data-stu-id="b4d9a-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="b4d9a-133">Créez une règle de publication web (par exemple, **Découverte automatique Lync Server (HTTP)**).</span><span class="sxs-lookup"><span data-stu-id="b4d9a-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="b4d9a-134">Dans **Nom public**, entrez lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="b4d9a-135">Sous l’onglet **Pontage**, sélectionnez uniquement l’option permettant d’établir un pont entre le port 80 et le port 8080 pour les requêtes.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="b4d9a-136">Sous l’onglet **Authentification**, sélectionnez **Aucune authentification** et **Le client ne peut pas s’authentifier directement**.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="b4d9a-137">Validez les modifications, puis déplacez la règle en haut de la liste des règles Lync (première dans l’ordre de traitement).</span><span class="sxs-lookup"><span data-stu-id="b4d9a-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="b4d9a-138">Mobilité pour le déploiement dans un domaine séparé</span><span class="sxs-lookup"><span data-stu-id="b4d9a-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="b4d9a-139">Un espace d’adressage SIP, également appelé *domaine séparé* ou *déploiement hybride* est une configuration dans laquelle les utilisateurs sont déployés sur site et dans un environnement en ligne.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="b4d9a-140">L’objectif est de permettre à un utilisateur, quel que soit l’emplacement de son serveur central (sur site ou en ligne), de se connecter au déploiement et d’être redirigé vers l’emplacement de son serveur central.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="b4d9a-141">Pour ce faire, la fonctionnalité de découverte automatique de Microsoft Lync Server 2013 est utilisée pour rediriger l’utilisateur en ligne vers la topologie en ligne.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="b4d9a-142">Pour ce faire, vous devez configurer l’URL (Uniform Resource Locator) de découverte automatique à l’aide de Lync Server Management Shell et des cmdlets **Get-CsHostingProvider** et **Set-CsHostingProvider**.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="b4d9a-143">Vous devrez recueillir et enregistrer les attributs déployés suivants :</span><span class="sxs-lookup"><span data-stu-id="b4d9a-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="b4d9a-144">À partir de Lync Server Management Shell, tapez</span><span class="sxs-lookup"><span data-stu-id="b4d9a-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="b4d9a-p105">Dans les résultats, recherchez le fournisseur en ligne avec l’attribut **ProxyFQDN**. Par exemple, sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-p105">In the results, find the online provider with the attribute **ProxyFQDN**. For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="b4d9a-147">Enregistrez la valeur de l’attribut ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="b4d9a-148">Activer la Fédération dans le panneau de configuration Lync Server sur site, autorisant la Fédération avec le fournisseur en ligne</span><span class="sxs-lookup"><span data-stu-id="b4d9a-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="b4d9a-p106">Activez la fédération pour le fournisseur en ligne. Par défaut, tous les utilisateurs en ligne sont activés pour la fédération de domaine et peuvent communiquer avec tous les domaines.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-p106">Enable federation for the online provider. By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="b4d9a-151">Si vous envisagez de définir les domaines bloqués et autorisés, déterminez les domaines que vous autoriserez et bloquerez de façon explicite.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="b4d9a-152">Pour la fédération en ligne, vous devez planifier les exceptions de pare-feu, les certificats et les enregistrements d’hôte DNS (A ou AAAA, avec IPv6).</span><span class="sxs-lookup"><span data-stu-id="b4d9a-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="b4d9a-153">En outre, vous devez configurer les stratégies de fédération.</span><span class="sxs-lookup"><span data-stu-id="b4d9a-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="b4d9a-154">Pour plus d’informations, reportez-vous à la rubrique [Planning for Lync Server 2013 and Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="b4d9a-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

