---
title: 'Lync Server 2013 : présentation de la découverte automatique'
description: 'Lync Server 2013 : présentation de la découverte automatique.'
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
ms.openlocfilehash: 295aba4bffbe5d17070702203cfd933284cb12c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547350"
---
# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="53a47-103">Présentation de la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a47-103">Understanding Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53a47-104">_**Dernière modification de la rubrique :** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="53a47-104">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="53a47-105">Le service de découverte automatique Lync Server 2013 est une fonctionnalité qui a été initialement introduite dans Microsoft Lync Server 2010 dans le cadre de la mise à jour cumulative de Lync Server 2010:2011.</span><span class="sxs-lookup"><span data-stu-id="53a47-105">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="53a47-106">Outre les correctifs, cette mise à jour cumulative a fourni une prise en charge pour les clients Lync mobile et Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="53a47-106">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="53a47-107">Dans Lync Server 2013, le service de découverte automatique fait partie intégrante des clients mobiles externes et internes, et la découverte automatique est également étendue aux nouveaux clients, tels que l’application Lync Windows Store récemment introduite pour Windows 8.</span><span class="sxs-lookup"><span data-stu-id="53a47-107">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="53a47-108">La découverte automatique est également utilisée par les clients de bureau Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="53a47-108">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="53a47-109">La découverte automatique est reconnue dans Lync Server par les enregistrements DNS (Domain Name System) requis **lyncdiscover \<domain\> .**</span><span class="sxs-lookup"><span data-stu-id="53a47-109">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>**</span></span> <span data-ttu-id="53a47-110">et \*\*lyncdiscoverinternal. \<domain\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="53a47-110">and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="53a47-111">En outre, les versions plus récentes du client de bureau Lync 2010 et Lync 2013 préfèrent la découverte automatique sur les enregistrements SRV DNS (Domain Name System), à l’aide des enregistrements SRV DNS uniquement si lyncdiscover.\<domain\></span><span class="sxs-lookup"><span data-stu-id="53a47-111">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\></span></span> <span data-ttu-id="53a47-112">ou lyncdiscoverinternal.\<domain\></span><span class="sxs-lookup"><span data-stu-id="53a47-112">or lyncdiscoverinternal.\<domain\></span></span> <span data-ttu-id="53a47-113">ne répond pas ou ne se résout pas.</span><span class="sxs-lookup"><span data-stu-id="53a47-113">does not respond or does not resolve.</span></span> <span data-ttu-id="53a47-114">L’application Lync Windows Store pour Windows 8 et Lync mobile utilise exclusivement la découverte automatique et ne fait pas référence aux enregistrements DNS SRV traditionnels.</span><span class="sxs-lookup"><span data-stu-id="53a47-114">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="53a47-115">Dans Lync Server 2013, la découverte automatique est étendue pour communiquer au client les éléments, les fonctionnalités et les méthodes de communication disponibles pour le client.</span><span class="sxs-lookup"><span data-stu-id="53a47-115">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="53a47-116">Les informations sont communiquées par le biais d’une demande envoyée à partir du client et les services Web Lync Server répondent par une réponse clairement définie indiquant les éléments disponibles pour le client, ainsi que la façon de contacter ces fonctionnalités dans le format du document de réponse de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="53a47-116">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="53a47-117">La meilleure façon de comprendre le document de réponse de découverte automatique, y compris la façon dont les services Web communiquent les fonctionnalités aux clients par le biais de ce document, consiste à dissect et à définir chaque ligne dans une réponse classique du document de réponse de découverte automatique de Lync Web service.</span><span class="sxs-lookup"><span data-stu-id="53a47-117">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="53a47-118">Dans les détails suivants, l’utilisateur s’est déjà authentifié auprès du serveur associé en répondant à une demande d’authentification.</span><span class="sxs-lookup"><span data-stu-id="53a47-118">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="53a47-119">Le service Web de découverte automatique Lync est défini dans les <STRONG>protocoles Microsoft Office</STRONG> dans la section <STRONG>spécifications ouvertes</STRONG> de la bibliothèque MSDN ( <STRONG>Microsoft Developer Network</STRONG> ).</span><span class="sxs-lookup"><span data-stu-id="53a47-119">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="53a47-120">Pour plus d’informations, reportez-vous au document de spécification complet, « Lync Autodiscover Web service Protocol », à l’adresse suivante : <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A> .</span><span class="sxs-lookup"><span data-stu-id="53a47-120">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="53a47-121">Pour plus d’informations sur l’authentification, voir « OC Authentication Web service Protocol » à l’adresse <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A> .</span><span class="sxs-lookup"><span data-stu-id="53a47-121">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="53a47-122">Réponse de découverte automatique de service Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="53a47-122">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="53a47-123">La réponse renvoyée lors de l’envoi de la demande de découverte automatique est la même pour un client interne ou externe.</span><span class="sxs-lookup"><span data-stu-id="53a47-123">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="53a47-124">Certains paramètres qui sont compatibles avec l’emplacement peuvent changer.</span><span class="sxs-lookup"><span data-stu-id="53a47-124">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="53a47-125">Si une demande client est reçue, mais que le pool réel est différent de celui qui a été contacté, le pool d’accueil de l’utilisateur est défini pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="53a47-125">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="53a47-126">Un collègue dont le compte d’utilisateur se trouve sur un pool différent, mais qui se connecte à partir du même bureau, obtient une réponse légèrement différente.</span><span class="sxs-lookup"><span data-stu-id="53a47-126">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="53a47-127">La réponse indique le serveur frontal ou le pool frontal correct pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="53a47-127">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="53a47-128">Exemple de document de réponse de découverte automatique :</span><span class="sxs-lookup"><span data-stu-id="53a47-128">An example of an Autodiscover Response document:</span></span>

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

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="53a47-129">Informations sur le document de réponse de découverte automatique</span><span class="sxs-lookup"><span data-stu-id="53a47-129">Autodiscover Response Document Details</span></span>

<span data-ttu-id="53a47-130">Le document de réponse de découverte automatique peut être dans l’un des deux formats.</span><span class="sxs-lookup"><span data-stu-id="53a47-130">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="53a47-131">Le format par défaut est JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="53a47-131">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="53a47-132">L’autre format est le document XML (Extensible Markup Language).</span><span class="sxs-lookup"><span data-stu-id="53a47-132">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="53a47-133">Le code XML est utilisé pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="53a47-133">The XML is used for this example.</span></span> <span data-ttu-id="53a47-134">La demande et la réponse sont prévisibles, car le document possède un schéma défini qui détermine le format.</span><span class="sxs-lookup"><span data-stu-id="53a47-134">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="53a47-135">La ligne dans le document qui décrit le schéma utilisé est la première ligne de la demande ou de la réponse :</span><span class="sxs-lookup"><span data-stu-id="53a47-135">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="53a47-136">La définition de **AccessLocation = « External »** indique que la demande a été effectuée à partir d’un utilisateur externe.</span><span class="sxs-lookup"><span data-stu-id="53a47-136">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="53a47-137">SipServerInternalAccess et SipServerExternalAccess ne sont actuellement pas utilisés.</span><span class="sxs-lookup"><span data-stu-id="53a47-137">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="53a47-138">Ces entrées sont réservées pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="53a47-138">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="53a47-139">SipClientInternalAccess et SipClientExternalAccess décrivent le nom de domaine complet et le port qu’un client interne ou externe utilisera pour accéder au serveur SIP défini.</span><span class="sxs-lookup"><span data-stu-id="53a47-139">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="53a47-140">Le client de bureau Lync et l’application Lync du Windows Store utilisent ces entrées en fonction de leur emplacement (interne ou externe) pour rechercher le directeur ou le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="53a47-140">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="53a47-141">Les `Autodiscover` références contiennent les points d’entrée de service pour le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="53a47-141">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="53a47-142">L’attribut Token contient le nom du service et le href est une URL qui définit le client où se trouve le service.</span><span class="sxs-lookup"><span data-stu-id="53a47-142">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="53a47-143">Les clients sur un réseau externe utilisent le `External/Autodiscover` .</span><span class="sxs-lookup"><span data-stu-id="53a47-143">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="53a47-144">Le service de découverte automatique est installé dans le cadre du processus de déploiement.</span><span class="sxs-lookup"><span data-stu-id="53a47-144">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="53a47-145">`Internal/Autodiscover` n’est pas utilisé actuellement et est réservé à une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="53a47-145">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="53a47-146">Les `AuthBroker` références contiennent les points d’entrée de service pour le service de Broker d’authentification interne et externe, dans ce cas, SIP. svc.</span><span class="sxs-lookup"><span data-stu-id="53a47-146">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="53a47-147">L’attribut Token contient le nom du service et le href est une URL qui définit le client où se trouve le service.</span><span class="sxs-lookup"><span data-stu-id="53a47-147">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="53a47-148">Clients sur le réseau interne avec utilisation `Internal/AuthBroker` .</span><span class="sxs-lookup"><span data-stu-id="53a47-148">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="53a47-149">Les clients sur un réseau externe utilisent le `External/AuthBroker` .</span><span class="sxs-lookup"><span data-stu-id="53a47-149">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="53a47-150">Le service AuthBroker est installé dans le cadre du processus de déploiement de vos services Web de déploiement interne de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a47-150">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="53a47-151">Le `WebScheduler` jeton fait référence aux URL pour l’accès client à la planification Web pour les conférences Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53a47-151">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="53a47-152">Actuellement, seul le `External/WebScheduler` est utilisé.</span><span class="sxs-lookup"><span data-stu-id="53a47-152">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="53a47-153">Le WebScheduler est installé dans le cadre du processus de déploiement de vos services Web de déploiement interne de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a47-153">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="53a47-154">`Internal/Mcx` et `External/Mcx` sont les emplacements des services de mobilité, introduits dans la mise à jour cumulative de Lync Server 2010 : novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="53a47-154">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="53a47-155">Ces références continueront à être utilisées par Lync 2010 mobile sur tous les appareils pris en charge.</span><span class="sxs-lookup"><span data-stu-id="53a47-155">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="53a47-156">Le service MCX est installé dans le cadre du processus de déploiement de vos services Web de déploiement interne de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a47-156">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="53a47-157">**Internal/Ucwa**, **External/Ucwa** et **Ucwa** permettent aux clients d’accéder à l’interface de programmation d’applications Web Unified Communications (Ucwa API, ou simplement Ucwa).</span><span class="sxs-lookup"><span data-stu-id="53a47-157">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="53a47-158">`Internal/Ucwa` et les `External/Ucwa` répertoires virtuels sont des points d’accès réservés pour l’amélioration des fonctionnalités futures et ne sont pas utilisés.</span><span class="sxs-lookup"><span data-stu-id="53a47-158">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="53a47-159">Le `Ucwa` répertoire virtuel est utilisé pour Microsoft Lync mobile (introduit avec Lync Server 2013) sur tous les appareils pris en charge.</span><span class="sxs-lookup"><span data-stu-id="53a47-159">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="53a47-160">Le service UCWA est installé dans le cadre du processus de déploiement de vos services Web de déploiement interne de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a47-160">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="53a47-161">`Internal/XFrame`, **External/Xframe** et **Xframe** fournissent l’accès aux applications serveur basées sur UCWA.</span><span class="sxs-lookup"><span data-stu-id="53a47-161">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="53a47-162">XFrame est installé dans le cadre du processus de déploiement de vos services Web de déploiement interne de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a47-162">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="53a47-163">Le `Self` jeton fait référence à des informations spécifiques au client (type de réponse de l’utilisateur) qui effectue la demande.</span><span class="sxs-lookup"><span data-stu-id="53a47-163">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="53a47-164">Le client qui a effectué cette demande était externe et cette référence de découverte automatique concerne la partie utilisateur du service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="53a47-164">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53a47-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="53a47-165">See Also</span></span>


[<span data-ttu-id="53a47-166">Configuration système requise pour les composants d’accès des utilisateurs externes pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a47-166">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="53a47-167">Planification de la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a47-167">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

