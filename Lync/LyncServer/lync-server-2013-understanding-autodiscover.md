---
title: 'Lync Server 2013 : présentation de la découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9d885654f9222ce3d3e9fb7b03e9b388f0ca0a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="d0612-102">Comprendre la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0612-102">Understanding Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0612-103">_**Dernière modification de la rubrique :** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="d0612-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="d0612-104">Le service de découverte automatique de Lync Server 2013 est une fonctionnalité introduite dans Microsoft Lync Server 2010 dans le cadre de la mise à jour cumulative pour Lync Server 2010:2011.</span><span class="sxs-lookup"><span data-stu-id="d0612-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="d0612-105">Outre les correctifs, cette mise à jour cumulative a fourni une prise en charge pour les clients Lync mobile et Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d0612-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="d0612-106">Dans Lync Server 2013, le service de découverte automatique fait partie intégrante de l’utilisation des clients mobiles internes et externes, et la découverte automatique est également étendue aux nouveaux clients, tels que la dernière présentation de l’application Lync du Windows Store pour Windows 8.</span><span class="sxs-lookup"><span data-stu-id="d0612-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="d0612-107">La découverte automatique est également utilisée par le client de bureau 2013 Lync.</span><span class="sxs-lookup"><span data-stu-id="d0612-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="d0612-108">La découverte automatique est reconnue dans Lync Server par le système de noms de domaine (DNS) requis \*\*lyncdiscover.\< Domain\> \*\* et **lyncdiscoverinternal.\< Domain\>(domaine**).</span><span class="sxs-lookup"><span data-stu-id="d0612-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>** and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="d0612-109">De plus, les versions plus récentes de Lync 2010 et du client de bureau 2013 de Lync préfèrent la découverte automatique par le biais des enregistrements SRV DNS (Domain Name System), à l’aide des enregistrements SRV DNS uniquement si lyncdiscover. \<Domain\> ou lyncdiscoverinternal. \<le\> domaine ne répond pas ou n’est pas résolu.</span><span class="sxs-lookup"><span data-stu-id="d0612-109">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\> or lyncdiscoverinternal.\<domain\> does not respond or does not resolve.</span></span> <span data-ttu-id="d0612-110">L’application Lync du Windows Store pour Windows 8 et Lync mobile utilise uniquement la découverte automatique et ne fait pas référence aux enregistrements DNS SRV traditionnels.</span><span class="sxs-lookup"><span data-stu-id="d0612-110">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="d0612-111">Dans Lync Server 2013, la découverte automatique est développée pour communiquer au client les éléments, fonctionnalités et méthodes de communication disponibles pour le client.</span><span class="sxs-lookup"><span data-stu-id="d0612-111">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="d0612-112">Les informations sont communiquées par le biais d’une requête envoyée par le client, et les services Web de Lync Server répondent par une réponse clairement définie indiquant le nom du client et le mode de contact de ces fonctionnalités dans le format de la découverte automatique. Document de réponse.</span><span class="sxs-lookup"><span data-stu-id="d0612-112">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="d0612-113">La meilleure façon de comprendre le document de réponse de découverte automatique, y compris la façon dont les services Web communiquent les fonctionnalités aux clients par le biais de ce document, consiste à dissect et à définir chaque ligne dans une réponse standard du document de réponse de découverte automatique du service Web Lync.</span><span class="sxs-lookup"><span data-stu-id="d0612-113">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="d0612-114">Dans les détails qui suivent, l’utilisateur est déjà authentifié sur le serveur principal en réponse à une demande d’authentification.</span><span class="sxs-lookup"><span data-stu-id="d0612-114">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="d0612-115">Le service Web de découverte automatique Lync est défini dans les <STRONG>protocoles Microsoft Office</STRONG> dans la section <STRONG>spécifications ouvertes</STRONG> de la bibliothèque <STRONG>Microsoft Developer Network</STRONG> (MSDN).</span><span class="sxs-lookup"><span data-stu-id="d0612-115">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="d0612-116">Pour plus d’informations, reportez-vous au document de spécification complet « protocole de service Web <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>de découverte automatique » dans :.</span><span class="sxs-lookup"><span data-stu-id="d0612-116">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="d0612-117">Pour plus d’informations sur l’authentification, voir « protocole de service Web <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>d’authentification OC » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="d0612-117">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="d0612-118">La réponse de découverte automatique du service Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d0612-118">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="d0612-119">La réponse renvoyée lors de l’envoi de la demande de découverte automatique est identique pour un client interne ou externe.</span><span class="sxs-lookup"><span data-stu-id="d0612-119">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="d0612-120">Certains paramètres qui sont compatibles avec la localisation peuvent changer.</span><span class="sxs-lookup"><span data-stu-id="d0612-120">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="d0612-121">Si une requête client est reçue alors que le pool réel est différent de celui qui a été contacté, le groupe de ressources de famille de l’utilisateur est défini pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d0612-121">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="d0612-122">Un collègue dont le compte utilisateur se trouve sur un autre groupe, mais qui se connecte à partir du même bureau, obtiendrait une réponse légèrement différente.</span><span class="sxs-lookup"><span data-stu-id="d0612-122">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="d0612-123">La réponse indique le serveur frontal ou le pool frontal approprié pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d0612-123">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="d0612-124">Exemple de document de réponse de découverte automatique :</span><span class="sxs-lookup"><span data-stu-id="d0612-124">An example of an Autodiscover Response document:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="d0612-125">Détails du document de réponse automatique</span><span class="sxs-lookup"><span data-stu-id="d0612-125">Autodiscover Response Document Details</span></span>

<span data-ttu-id="d0612-126">Le document de réponse de découverte automatique peut être dans l’un des deux formats proposés.</span><span class="sxs-lookup"><span data-stu-id="d0612-126">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="d0612-127">Le format par défaut est JSON (JavaScript Object Notation).</span><span class="sxs-lookup"><span data-stu-id="d0612-127">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="d0612-128">Le format autre est le document XML (Extensible Markup Language).</span><span class="sxs-lookup"><span data-stu-id="d0612-128">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="d0612-129">Le code XML est utilisé pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="d0612-129">The XML is used for this example.</span></span> <span data-ttu-id="d0612-130">La requête et la réponse sont prévisibles, car le document est doté d’un schéma défini qui détermine le format.</span><span class="sxs-lookup"><span data-stu-id="d0612-130">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="d0612-131">La ligne du document qui décrit le schéma utilisé est la première ligne de la requête ou de la réponse :</span><span class="sxs-lookup"><span data-stu-id="d0612-131">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="d0612-132">La définition de **AccessLocation = "External"** indique que la requête a été effectuée à partir d’un utilisateur externe.</span><span class="sxs-lookup"><span data-stu-id="d0612-132">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="d0612-133">Les SipServerInternalAccess et SipServerExternalAccess ne sont pas utilisés actuellement.</span><span class="sxs-lookup"><span data-stu-id="d0612-133">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="d0612-134">Ces entrées sont réservées pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d0612-134">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="d0612-135">SipClientInternalAccess et SipClientExternalAccess décrivent le nom de domaine et le port complets qu’un client interne ou externe utilisera pour accéder au serveur SIP défini.</span><span class="sxs-lookup"><span data-stu-id="d0612-135">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="d0612-136">Le client de bureau Lync et l’application Lync du Windows Store utilisent ces entrées en fonction de leur emplacement (interne ou externe) pour trouver le directeur ou le serveur principal.</span><span class="sxs-lookup"><span data-stu-id="d0612-136">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="d0612-137">Les `Autodiscover` références contiennent les points d’entrée de service pour le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="d0612-137">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="d0612-138">L’attribut Token contient le nom du service, et la clé href est une URL qui définit pour le client où le service est disponible.</span><span class="sxs-lookup"><span data-stu-id="d0612-138">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="d0612-139">Les clients sur un réseau externe utilisent `External/Autodiscover`le.</span><span class="sxs-lookup"><span data-stu-id="d0612-139">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="d0612-140">Le service de découverte automatique est installé dans le cadre du processus de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d0612-140">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="d0612-141">`Internal/Autodiscover`n’est pas utilisé et est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d0612-141">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="d0612-142">Les `AuthBroker` références contiennent les points d’entrée de service pour le service de Broker d’identification interne et externe (par exemple, SIP. svc).</span><span class="sxs-lookup"><span data-stu-id="d0612-142">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="d0612-143">L’attribut Token contient le nom du service, et la clé href est une URL qui définit pour le client où le service est disponible.</span><span class="sxs-lookup"><span data-stu-id="d0612-143">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="d0612-144">Clients du réseau interne à utiliser `Internal/AuthBroker`.</span><span class="sxs-lookup"><span data-stu-id="d0612-144">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="d0612-145">Les clients sur un réseau externe utilisent `External/AuthBroker`le.</span><span class="sxs-lookup"><span data-stu-id="d0612-145">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="d0612-146">Le service AuthBroker est installé dans le cadre du processus de déploiement de vos services Web de déploiement de Lync Server 2013 internes.</span><span class="sxs-lookup"><span data-stu-id="d0612-146">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="d0612-147">Le `WebScheduler` jeton fait référence aux URL relatives à l’accès client aux conférences sur le Web pour les conférences Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d0612-147">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="d0612-148">Pour l’instant, `External/WebScheduler` seul le est utilisé.</span><span class="sxs-lookup"><span data-stu-id="d0612-148">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="d0612-149">Le WebScheduler est installé dans le cadre de la procédure de déploiement de vos services Web de déploiement de Lync Server 2013 internes.</span><span class="sxs-lookup"><span data-stu-id="d0612-149">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="d0612-150">`Internal/Mcx`et `External/Mcx` sont les emplacements des services de mobilité, introduits dans une mise à jour cumulative pour Lync Server 2010 : novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="d0612-150">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="d0612-151">Ces références seront toujours utilisées par Lync 2010 mobile sur tous les appareils pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d0612-151">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="d0612-152">Le service MCX est installé dans le cadre du processus de déploiement de vos services Web de déploiement de Lync Server 2013 internes.</span><span class="sxs-lookup"><span data-stu-id="d0612-152">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="d0612-153">**Internal/Ucwa**, **External/Ucwa** et **Ucwa** permettent aux clients d’accéder à l’interface de programmation d’application Web Unified Communications (API Ucwa, ou simplement Ucwa).</span><span class="sxs-lookup"><span data-stu-id="d0612-153">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="d0612-154">`Internal/Ucwa`les `External/Ucwa` répertoires virtuels sont des points d’accès réservés pour une future amélioration des fonctionnalités, et ne sont pas utilisés.</span><span class="sxs-lookup"><span data-stu-id="d0612-154">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="d0612-155">Le `Ucwa` répertoire virtuel est utilisé pour Microsoft Lync mobile (introduit avec Lync Server 2013) sur tous les appareils pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d0612-155">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="d0612-156">Le service UCWA est installé dans le cadre du processus de déploiement de vos services Web de déploiement de Lync Server 2013 internes.</span><span class="sxs-lookup"><span data-stu-id="d0612-156">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="d0612-157">`Internal/XFrame`, **Externe/Xframe** et **Xframe** offrent un accès aux applications serveur UCWA.</span><span class="sxs-lookup"><span data-stu-id="d0612-157">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="d0612-158">XFrame est installé dans le cadre du processus de déploiement de vos services Web de déploiement de Lync Server 2013 internes.</span><span class="sxs-lookup"><span data-stu-id="d0612-158">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="d0612-159">Le `Self` jeton fait référence à des informations spécifiques au client (type de réponse de l’utilisateur) qui effectue la requête.</span><span class="sxs-lookup"><span data-stu-id="d0612-159">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="d0612-160">Le client qui a effectué cette demande était externe, et cette référence de découverte automatique correspond à la partie utilisateur du service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="d0612-160">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d0612-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d0612-161">See Also</span></span>


[<span data-ttu-id="d0612-162">Configuration système requise pour les composants d’accès des utilisateurs externes pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0612-162">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="d0612-163">Planification de la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0612-163">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

