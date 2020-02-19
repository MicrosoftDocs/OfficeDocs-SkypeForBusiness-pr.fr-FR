---
title: Afficher les applications serveur MSPL (Microsoft SIP Processing Language)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb195ee5826cbb63f7fc718a038761f10199135
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="4d533-102">Afficher les applications serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d533-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d533-103">_**Dernière modification de la rubrique :** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="4d533-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="4d533-104">Une application serveur MSPL (Microsoft SIP Processing Language) est une application script uniquement qui utilise un langage de script au lieu de l’API 2010 de Microsoft Lync.</span><span class="sxs-lookup"><span data-stu-id="4d533-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="4d533-105">Outre la capacité de contrôler avec une plus grande précision les comportements de filtrage et proxy, le langage MSPL offre un procédé qui permet de répartir des messages spécifiques vers des applications SIP fondées sur des transactions.</span><span class="sxs-lookup"><span data-stu-id="4d533-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="4d533-106">Le langage MSPL est plus particulièrement utilisé pour le filtrage et le routage des messages SIP.</span><span class="sxs-lookup"><span data-stu-id="4d533-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="4d533-107">Les applications MSPL s’exécutent dans le même processus que le module UserServices, tandis qu’un programme basé sur l’API 2010 de Lync s’exécute dans un processus distinct.</span><span class="sxs-lookup"><span data-stu-id="4d533-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="4d533-108">Vous pouvez utiliser la page **application serveur** du groupe **topologie** du panneau de configuration Lync Server pour afficher la liste des applications serveur MSPL qui s’exécutent sur les serveurs frontaux dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d533-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="4d533-109">La liste affiche les scripts disponibles pour chaque pool et indique s’ils sont activés ou critiques.</span><span class="sxs-lookup"><span data-stu-id="4d533-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="4d533-110">Les scripts sont exécutés dans l’ordre où ils apparaissent dans la liste.</span><span class="sxs-lookup"><span data-stu-id="4d533-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="4d533-111">Ces scripts comportent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4d533-111">These scripts include the following:</span></span>

  - <span data-ttu-id="4d533-p103">ClientVersionFilter permet à l’administrateur de spécifier la version des clients pris en charge dans un pool. Le filtre de version du client vérifie la version du client et peut soit empêcher le client de se connecter, soit présenter à l’utilisateur un message indiquant qu’il utilise un client non pris en charge. Ce filtre peut également être configuré pour afficher un message contenant l’URL d’accès à la dernière version téléchargeable du client.</span><span class="sxs-lookup"><span data-stu-id="4d533-p103">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool. The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported. The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="4d533-115">TranslationService permet de convertir un numéro qu’un utilisateur compose vers un numéro E.164, conformément aux règles de normalisation définies par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="4d533-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="4d533-116">Pour plus d’informations, consultez la rubrique [règles de conversion dans Lync Server 2013](lync-server-2013-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="4d533-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="4d533-117">IncomingFederation impose la validation de la fédération au niveau du locataire pour les messages entre locataires et entrants en provenance de déploiements externes.</span><span class="sxs-lookup"><span data-stu-id="4d533-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="4d533-p105">UserServices est le composant de serveur d’inscriptions SIP, de présence et de conférence d’un serveur frontal. Il propose des fonctionnalités très intégrées de messagerie instantanée, de présence et de conférence greffées sur le proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="4d533-p105">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server. It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="4d533-120">InterClusterRouting est chargé du routage des appels vers le pool de serveurs d’inscriptions principal de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4d533-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="4d533-121">Pour plus d’informations, consultez la rubrique [composants voix sur les serveurs frontaux pour Lync server 2013](lync-server-2013-front-end-server-voip-components.md).</span><span class="sxs-lookup"><span data-stu-id="4d533-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="4d533-122">IIMFilter (filtre de message instantané intelligent) bloque les messages qui contiennent des URL interactives ou qui tentent de lancer des transferts de fichiers.</span><span class="sxs-lookup"><span data-stu-id="4d533-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="4d533-123">IIMFilter vérifie également la version du client pour le compte du serveur.</span><span class="sxs-lookup"><span data-stu-id="4d533-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="4d533-124">IIMFilter affecte les transferts de fichiers qui sont lancés à l’aide de Lync Server ou de Communicator.</span><span class="sxs-lookup"><span data-stu-id="4d533-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="4d533-125">Par défaut, les liens interactifs sont désactivés en ajoutant un caractère de soulignement avant le premier caractère du lien.</span><span class="sxs-lookup"><span data-stu-id="4d533-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="4d533-126">Un administrateur peut modifier ce comportement afin que le lien soit bloqué, auquel cas les messages qui contiennent des URL interactives ou qui tentent de lancer un transfert de fichier sont bloqués par le serveur pour atteindre leurs destinations prévues.</span><span class="sxs-lookup"><span data-stu-id="4d533-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="4d533-127">IIMFilter est installé sur tous les serveurs exécutant Lync Server, à l’exception des serveurs proxy et des serveurs d’archivage.</span><span class="sxs-lookup"><span data-stu-id="4d533-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="4d533-128">UserPinService sert à vérifier les codes confidentiels dans le cadre des conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="4d533-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="4d533-129">DefaultRouting est l’application de routage par défaut pour les serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d533-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="4d533-130">Elle est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="4d533-130">It is enabled by default.</span></span> <span data-ttu-id="4d533-131">L’application de routage est installée sur tous les serveurs Standard Edition et Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4d533-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="4d533-p109">ExumRouting achemine les appels vers la messagerie unifiée Exchange Server. ExumRouting détermine le serveur de messagerie unifiée Exchange approprié vers lequel acheminer l’appel en présence d’un nouveau message vocal à déposer. ExumRouting gère également d’autres aspects d’intégration de la messagerie unifiée Exchange, notamment le routage vers le standard automatique et l’accès abonné.</span><span class="sxs-lookup"><span data-stu-id="4d533-p109">ExumRouting routes calls to Exchange Server Unified Messaging (UM). ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit. ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="4d533-p110">OutboundRouting détermine la passerelle qui achemine un appel vers un numéro de téléphone en fonction du numéro composé et de l’autorisation de numérotation de l’utilisateur. OutboundRouting gère également le réacheminement des appels si une passerelle n’est pas en mesure de traiter un appel.</span><span class="sxs-lookup"><span data-stu-id="4d533-p110">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization. OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="4d533-137">QoEAgent réceptionne les rapports de données de qualité de l’expérience (QoE) en provenance des systèmes d’extrémité par le biais de demandes de service SIP, puis transmet les données à la file d’attente de destination sur le serveur de surveillance ou à des consommateurs tiers via HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="4d533-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="4d533-138">Pour plus d’informations, reportez-vous à la rubrique [Deploying Monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="4d533-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="4d533-139">OutgoingFederation impose la validation de la fédération au niveau du locataire pour les messages à destination d’un déploiement externe ciblé.</span><span class="sxs-lookup"><span data-stu-id="4d533-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="4d533-140">AcpRouting redirige via proxy les demandes INVITE les demandes destinées au fournisseur de services d’audioconférence vers la passerelle de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="4d533-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="4d533-141">Les scripts exécutés sur des serveurs Edge comprennent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4d533-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="4d533-142">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="4d533-142">IIMFilter</span></span>

  - <span data-ttu-id="4d533-143">OptionsHandler répond aux demandes entrantes OPTIONS par **200 OK** si la demande est destinée au serveur actuel.</span><span class="sxs-lookup"><span data-stu-id="4d533-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="4d533-144">Cet élément est utilisé dans le cadre de la validation des topologies.</span><span class="sxs-lookup"><span data-stu-id="4d533-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4d533-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4d533-145">See Also</span></span>


[<span data-ttu-id="4d533-146">Activer ou désactiver une application serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d533-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="4d533-147">Marquer une application MSPL (Microsoft SIP Processing Language) comme critique ou non critique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d533-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

