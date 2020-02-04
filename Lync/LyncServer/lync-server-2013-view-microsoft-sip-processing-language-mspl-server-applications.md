---
title: Afficher des applications de serveur MSPL (Microsoft SIP Processing Language)
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
ms.openlocfilehash: 63c1ce638e6bc9509c8faf46b39989b366f610a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="10b3b-102">Afficher des applications de serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10b3b-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10b3b-103">_**Dernière modification de la rubrique :** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="10b3b-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="10b3b-104">Une application serveur Microsoft SIP Processing Language (MSPL) est une application de script uniquement qui utilise un langage de script au lieu de l’API 2010 Microsoft Lync.</span><span class="sxs-lookup"><span data-stu-id="10b3b-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="10b3b-105">MSPL fournit un contrôle plus précis sur le filtrage et les comportements de proxy, en plus d’une installation permettant de distribuer des messages spécifiques aux applications SIP en fonction des transactions.</span><span class="sxs-lookup"><span data-stu-id="10b3b-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="10b3b-106">Le MSPL est utilisé spécifiquement pour filtrer et acheminer les messages SIP.</span><span class="sxs-lookup"><span data-stu-id="10b3b-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="10b3b-107">Les applications MSPL s’exécutent dans le même processus que le module UserServices, tandis qu’un programme basé sur l’API 2010 Lync s’exécute dans un processus distinct.</span><span class="sxs-lookup"><span data-stu-id="10b3b-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="10b3b-108">Vous pouvez utiliser la page de l' **application serveur** dans le groupe **topologie** du panneau de configuration de Lync Server pour afficher une liste des applications serveur MSPL qui s’exécutent sur des serveurs frontaux dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="10b3b-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="10b3b-109">La liste affiche les scripts disponibles pour chaque liste, ainsi que leur activation ou leur importance critique.</span><span class="sxs-lookup"><span data-stu-id="10b3b-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="10b3b-110">Les scripts s’exécutent dans l’ordre dans lequel ils apparaissent.</span><span class="sxs-lookup"><span data-stu-id="10b3b-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="10b3b-111">Ces scripts incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="10b3b-111">These scripts include the following:</span></span>

  - <span data-ttu-id="10b3b-112">ClientVersionFilter fournit à l’administrateur un moyen de spécifier la version des clients pris en charge par un pool.</span><span class="sxs-lookup"><span data-stu-id="10b3b-112">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool.</span></span> <span data-ttu-id="10b3b-113">Le filtre de version du client vérifie la version du client et peut soit empêcher le client de se connecter, soit en présenter un message indiquant qu’il utilise un client qui n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="10b3b-113">The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported.</span></span> <span data-ttu-id="10b3b-114">Le filtre de version du client peut également être configuré pour afficher un message destiné à l’utilisateur, qui contient l’URL de la version téléchargeable la plus récente du client.</span><span class="sxs-lookup"><span data-stu-id="10b3b-114">The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="10b3b-115">TranslationService convertit un nombre qu’un utilisateur compose vers un numéro E. 164 conformément aux règles de normalisation définies par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="10b3b-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="10b3b-116">Pour plus d’informations, voir [règles de traduction dans Lync Server 2013](lync-server-2013-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="10b3b-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="10b3b-117">IncomingFederation applique la validation de la Fédération au niveau du client pour les messages entrants et inter-locataire provenant de déploiements externes.</span><span class="sxs-lookup"><span data-stu-id="10b3b-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="10b3b-118">UserServices est le composant d’inscription SIP, de présence et de conférence d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="10b3b-118">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server.</span></span> <span data-ttu-id="10b3b-119">Ce service offre des fonctionnalités de messagerie instantanée, de présence et de conférence étroitement intégrées, intégrées au-dessus du proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="10b3b-119">It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="10b3b-120">InterClusterRouting est responsable du routage des appels vers le pool d’inscriptions principal de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="10b3b-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="10b3b-121">Pour plus d’informations, reportez-vous à la rubrique [composants VoIP serveur front-end pour Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span><span class="sxs-lookup"><span data-stu-id="10b3b-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="10b3b-122">IIMFilter (filtre de messages instantanés intelligents) bloque les messages qui contiennent des URL cliquables ou qui tentent d’initialiser des transferts de fichiers.</span><span class="sxs-lookup"><span data-stu-id="10b3b-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="10b3b-123">IIMFilter vérifie également la version du client pour le compte du serveur.</span><span class="sxs-lookup"><span data-stu-id="10b3b-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="10b3b-124">IIMFilter affecte les transferts de fichiers initiés via Lync Server ou Communicator.</span><span class="sxs-lookup"><span data-stu-id="10b3b-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="10b3b-125">Par défaut, les liens hypertexte peuvent être désactivés en ajoutant un trait de soulignement avant le premier caractère du lien.</span><span class="sxs-lookup"><span data-stu-id="10b3b-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="10b3b-126">Un administrateur peut modifier ce comportement de manière à ce que le lien soit bloqué, auquel cas les messages qui contiennent des URL sur lesquelles vous pouvez cliquer ou qui essaient de lancer un transfert de fichier sont bloqués par le serveur pour atteindre les destinations prévues.</span><span class="sxs-lookup"><span data-stu-id="10b3b-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="10b3b-127">IIMFilter est installé sur tous les serveurs exécutant Lync Server, à l’exception des serveurs proxy et des serveurs d’archivage.</span><span class="sxs-lookup"><span data-stu-id="10b3b-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="10b3b-128">UserPinService est utilisé pour vérifier les codes confidentiels (pin) de l’utilisateur pour les conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="10b3b-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="10b3b-129">DefaultRouting est l’application de routage par défaut pour les serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="10b3b-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="10b3b-130">Elle est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="10b3b-130">It is enabled by default.</span></span> <span data-ttu-id="10b3b-131">L’application de routage est installée sur tous les serveurs Standard Edition et Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="10b3b-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="10b3b-132">ExumRouting route les appels vers la messagerie unifiée Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="10b3b-132">ExumRouting routes calls to Exchange Server Unified Messaging (UM).</span></span> <span data-ttu-id="10b3b-133">ExumRouting détermine le serveur Exchange UM approprié pour diriger l’appel lorsqu’un nouveau message vocal doit être déposé.</span><span class="sxs-lookup"><span data-stu-id="10b3b-133">ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit.</span></span> <span data-ttu-id="10b3b-134">ExumRouting gère également d’autres aspects d’intégration de la messagerie unifiée Exchange, notamment le routage vers le standard automatique et l’accès de l’abonné.</span><span class="sxs-lookup"><span data-stu-id="10b3b-134">ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="10b3b-135">OutboundRouting détermine la passerelle qui route un appel vers un numéro de téléphone en fonction du numéro composé et de l’autorisation de numérotation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="10b3b-135">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization.</span></span> <span data-ttu-id="10b3b-136">OutboundRouting gère également le reroutage des appels si une passerelle ne peut pas traiter un appel.</span><span class="sxs-lookup"><span data-stu-id="10b3b-136">OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="10b3b-137">QoEAgent reçoit des rapports de données de qualité d’utilisation (QoE) de points de terminaison par le biais de demandes de SERVICE SIP et envoie les données à la file d’attente de destination sur le serveur de surveillance ou auprès de clients tiers à l’aide de HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="10b3b-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="10b3b-138">Pour plus d’informations, reportez-vous à la rubrique [déploiement de la surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="10b3b-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="10b3b-139">OutgoingFederation applique la validation de la Fédération au niveau du client pour les messages dirigés vers un déploiement externe ciblé.</span><span class="sxs-lookup"><span data-stu-id="10b3b-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="10b3b-140">Les proxys AcpRouting invitent les demandes destinées au fournisseur de services d’audioconférence à la passerelle du fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="10b3b-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="10b3b-141">Les scripts qui s’exécutent sur des serveurs Edge incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="10b3b-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="10b3b-142">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="10b3b-142">IIMFilter</span></span>

  - <span data-ttu-id="10b3b-143">OptionsHandler répond aux demandes d’OPTIONS entrantes avec **200 OK** si la requête est destinée au serveur actuel.</span><span class="sxs-lookup"><span data-stu-id="10b3b-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="10b3b-144">Cette opération est utilisée pour la validation de la topologie.</span><span class="sxs-lookup"><span data-stu-id="10b3b-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="10b3b-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10b3b-145">See Also</span></span>


[<span data-ttu-id="10b3b-146">Activer ou désactiver une application serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10b3b-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="10b3b-147">Marquer une application Microsoft SIP Processing Language (MSPL) comme critique ou non critique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10b3b-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

