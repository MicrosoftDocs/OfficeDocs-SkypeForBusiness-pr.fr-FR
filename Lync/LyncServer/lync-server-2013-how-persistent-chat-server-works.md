---
title: 'Lync Server 2013 : fonctionnement du serveur de conversation permanente'
description: 'Lync Server 2013 : fonctionnement du serveur de conversation permanente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c65df6a13305f75a8a25b85a39688fadf64e476c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562960"
---
# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="ca499-103">Fonctionnement du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca499-103">How Persistent Chat Server works in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca499-104">_**Dernière modification de la rubrique :** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="ca499-104">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="ca499-105">Lync Server 2013, serveur de conversation permanente vous permet de participer à des conversations en plusieurs rubriques, qui sont conservées au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="ca499-105">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="ca499-106">Le serveur de conversation permanente peut aider votre organisation à effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ca499-106">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="ca499-107">améliorer la communication entre les équipes géographiquement dispersées et multifonctionnelles ;</span><span class="sxs-lookup"><span data-stu-id="ca499-107">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="ca499-108">élargir la prise en compte des informations et la participation ;</span><span class="sxs-lookup"><span data-stu-id="ca499-108">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="ca499-109">améliorer la communication dans l’ensemble de votre organisation ;</span><span class="sxs-lookup"><span data-stu-id="ca499-109">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="ca499-110">réduire la surcharge d’informations ;</span><span class="sxs-lookup"><span data-stu-id="ca499-110">Reduce information overload</span></span>

  - <span data-ttu-id="ca499-111">améliorer la prise en compte des informations ;</span><span class="sxs-lookup"><span data-stu-id="ca499-111">Improve information awareness</span></span>

  - <span data-ttu-id="ca499-112">accroître la dissémination des connaissances et des informations importantes.</span><span class="sxs-lookup"><span data-stu-id="ca499-112">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="ca499-113">Vous pouvez déployer le serveur de conversation permanente comme un rôle facultatif avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca499-113">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="ca499-114">Les services de conversation permanente s’exécutent sur un pool dédié et un pool de serveurs de conversation permanente dépend d’un pool Lync Server pour acheminer les messages vers celui-ci.</span><span class="sxs-lookup"><span data-stu-id="ca499-114">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="ca499-115">Les clients utilisent le protocole XCCOS (eXtensible Chat Communication Over SIP).</span><span class="sxs-lookup"><span data-stu-id="ca499-115">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="ca499-116">Les serveurs frontaux Lync Server sont configurés pour acheminer le trafic vers un pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="ca499-116">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="ca499-117">Architecture de haut niveau</span><span class="sxs-lookup"><span data-stu-id="ca499-117">High-Level Architecture</span></span>

<span data-ttu-id="ca499-118">Les diagrammes suivants fournissent des perspectives de haut niveau de l’architecture et des services du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="ca499-118">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="ca499-119">**Architecture de haut niveau du serveur de conversation permanente**</span><span class="sxs-lookup"><span data-stu-id="ca499-119">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="ca499-120">![Architecture de serveur de conversation permanente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Architecture de serveur de conversation permanente.")</span><span class="sxs-lookup"><span data-stu-id="ca499-120">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="ca499-121">**Services de haut niveau du serveur de conversation permanente**</span><span class="sxs-lookup"><span data-stu-id="ca499-121">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="ca499-122">![Composants de serveur de conversation permanente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Composants de serveur de conversation permanente.")</span><span class="sxs-lookup"><span data-stu-id="ca499-122">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="ca499-123">Deux services s’exécutent sur les serveurs frontaux du serveur de conversation permanente :</span><span class="sxs-lookup"><span data-stu-id="ca499-123">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="ca499-124">Conversation permanente (canal)</span><span class="sxs-lookup"><span data-stu-id="ca499-124">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="ca499-125">Conformité</span><span class="sxs-lookup"><span data-stu-id="ca499-125">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="ca499-126">Service de conversation permanente (canal)</span><span class="sxs-lookup"><span data-stu-id="ca499-126">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="ca499-127">Le service de conversation permanente (canal) est le service principal responsable du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="ca499-127">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="ca499-128">Ce service offre les fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ca499-128">This service provides the following functions:</span></span>

  - <span data-ttu-id="ca499-129">acceptation des messages entrants ;</span><span class="sxs-lookup"><span data-stu-id="ca499-129">Accepts incoming messages</span></span>

  - <span data-ttu-id="ca499-130">Inscrit et répertorie les participants en ligne dans une salle de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ca499-130">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="ca499-131">retransmission des messages vers les abonnés à d’autres canaux ;</span><span class="sxs-lookup"><span data-stu-id="ca499-131">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="ca499-132">implémentation de la logique de gestion des canaux, d’invitation aux salles de conversation, de recherche et de notifications de nouveau contenu.</span><span class="sxs-lookup"><span data-stu-id="ca499-132">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="ca499-133">Le service de conversation permanente (canal) stocke et accède au contenu de la salle de conversation et à d’autres métadonnées système (règles d’autorisation, etc.) à l’aide de la Banque de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="ca499-133">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="ca499-134">Ce service stocke les fichiers chargés dans les salles de conversation du magasin de fichiers de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="ca499-134">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="ca499-135">Service de conformité</span><span class="sxs-lookup"><span data-stu-id="ca499-135">Compliance Service</span></span>

<span data-ttu-id="ca499-136">Le service de conformité est un composant facultatif du serveur de conversation permanente et est responsable de l’archivage du contenu et des événements de conversation dans le magasin de conformité de la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="ca499-136">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="ca499-137">Si votre organisation a des réglementations qui nécessitent l’archivage de l’activité de conversation permanente, vous pouvez déployer le service de conformité de conversation permanente facultatif.</span><span class="sxs-lookup"><span data-stu-id="ca499-137">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="ca499-138">Le service de conformité est installé sur chaque serveur de conversation permanente d’un pool de conversations permanentes.</span><span class="sxs-lookup"><span data-stu-id="ca499-138">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="ca499-139">Une fois configurée, la conformité du serveur de conversation permanente enregistre les activités de l’utilisateur, telles que la jonction et la fermeture des salles, ainsi que la publication et la lecture des messages.</span><span class="sxs-lookup"><span data-stu-id="ca499-139">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="ca499-140">Le service de conformité stocke les fichiers qui doivent être archivés dans le magasin de fichiers de conformité de la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="ca499-140">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="ca499-141">Services Web de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ca499-141">Persistent Chat Web Services</span></span>

<span data-ttu-id="ca499-142">Sur les serveurs frontaux Lync Server, deux services exécutés dépendent des services IIS (Internet Information Services) et sont implémentés en tant que composants Web :</span><span class="sxs-lookup"><span data-stu-id="ca499-142">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="ca499-143">**Services Web de conversation permanente pour le chargement/téléchargement de fichiers** Responsable de la publication et de l’extraction de fichiers à partir de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="ca499-143">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="ca499-144">**Services Web de conversation permanente pour la gestion des salles de conversation** Chargé de fournir aux utilisateurs la possibilité de gérer leurs salles de conversation et de créer de nouvelles salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="ca499-144">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="ca499-145">Comment puis-je commencer à utiliser le serveur de conversation permanente ?</span><span class="sxs-lookup"><span data-stu-id="ca499-145">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="ca499-146">Le serveur de conversation permanente est un rôle serveur facultatif au sein de l’infrastructure Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca499-146">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="ca499-147">Si vous installez le rôle de serveur de conversation permanente, tous les utilisateurs qui ont été activés par le biais d’une stratégie par un administrateur peuvent utiliser la conversation permanente avec le client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ca499-147">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="ca499-148">Pour plus d’informations sur le déploiement du serveur de conversation permanente et sur la façon dont les utilisateurs peuvent tirer parti des fonctionnalités par le biais d’une stratégie, voir [Deploying persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="ca499-148">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="ca499-149">Pour plus d’informations sur la configuration des paramètres de votre déploiement de serveur de conversation permanente, voir [Deploying persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) et [Managing Lync Server 2013, persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="ca499-149">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="ca499-150">Pour plus d’informations sur la façon d’activer les utilisateurs par une stratégie de sorte qu’ils puissent utiliser la fonctionnalité de conversation permanente dans le client Lync 2013, consultez la rubrique [Deploying persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) et [Managing Lync Server 2013, persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="ca499-150">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="ca499-151">Si vous avez déployé la conformité de la conversation permanente, reportez-vous à la rubrique [Managing Lync Server 2013, persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) pour plus d’informations sur la configuration des paramètres de conformité.</span><span class="sxs-lookup"><span data-stu-id="ca499-151">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="ca499-152">Flux d’appels de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ca499-152">Persistent Chat Call Flows</span></span>

<span data-ttu-id="ca499-153">Le client de conversation permanente communique avec le service de conversation permanente à l’aide de XCCOS.</span><span class="sxs-lookup"><span data-stu-id="ca499-153">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="ca499-154">Les séquences suivantes décrivent le processus de connexion, ainsi qu’un scénario classique d’abonnement à une salle et de publication de messages.</span><span class="sxs-lookup"><span data-stu-id="ca499-154">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="ca499-155">Connexion</span><span class="sxs-lookup"><span data-stu-id="ca499-155">Sign-in</span></span>

<span data-ttu-id="ca499-156">Le diagramme de flux d’appels et les étapes suivants décrivent le processus de connexion.</span><span class="sxs-lookup"><span data-stu-id="ca499-156">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="ca499-157">**Flux d’appels de connexion au client de conversation permanente**</span><span class="sxs-lookup"><span data-stu-id="ca499-157">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="ca499-158">![Diagramme de flux d’appels de serveur de conversation permanente.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagramme de flux d’appels de serveur de conversation permanente.")</span><span class="sxs-lookup"><span data-stu-id="ca499-158">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="ca499-159">Le client de conversation permanente envoie d’abord un abonnement SIP pour récupérer le document de mise en service intrabande à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="ca499-159">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="ca499-160">Ce document indique si la conversation permanente est activée ou désactivée pour l’utilisateur et la liste des URI SIP pour le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="ca499-160">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="ca499-161">Le client de conversation permanente envoie un message d’INVITE SIP à l’URI SIP du serveur de conversation permanente qu’il a obtenu à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="ca499-161">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="ca499-162">La séquence INVITE est suivie de 200 OK et ACK, et le client de conversation permanente a ouvert une session SIP avec un point de terminaison de serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="ca499-162">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="ca499-163">Par conséquent, le client de conversation permanente communique avec le serveur de conversation permanente en envoyant des messages d’informations SIP contenant des messages de conversation ou des commandes demandant au serveur d’effectuer une action.</span><span class="sxs-lookup"><span data-stu-id="ca499-163">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="ca499-164">Tous ces messages sont reconnus avec 200 OK ou le service 503 indisponible (en cas de charge importante sur le serveur).</span><span class="sxs-lookup"><span data-stu-id="ca499-164">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="ca499-165">Si le client reçoit une réponse 503, il retentera le message.</span><span class="sxs-lookup"><span data-stu-id="ca499-165">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="ca499-166">(Cet exemple n’inclut pas de réponse 503.) Si le serveur accepte le message ou la commande et envoie 200 OK, il fournit une réponse au client sous la forme d’un message INFO SIP distinct.</span><span class="sxs-lookup"><span data-stu-id="ca499-166">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="ca499-167">Cette réponse inclut une référence à la commande d’origine.</span><span class="sxs-lookup"><span data-stu-id="ca499-167">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="ca499-168">Le client de conversation permanente envoie un message d’informations SIP contenant la commande XCCOS **GetServerInfo** .</span><span class="sxs-lookup"><span data-stu-id="ca499-168">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="ca499-169">Le serveur de conversation permanente répond avec un nouveau message d’informations SIP contenant des informations sur la configuration du service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="ca499-169">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="ca499-170">Le client de conversation permanente envoie un message d’informations SIP contenant la commande XCCOS **GetAssociations** .</span><span class="sxs-lookup"><span data-stu-id="ca499-170">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="ca499-171">Le serveur de conversation permanente répond avec un nouveau message d’informations SIP contenant la liste des salles dont l’utilisateur est membre.</span><span class="sxs-lookup"><span data-stu-id="ca499-171">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="ca499-172">Le client de conversation permanente répète la commande pour récupérer la liste des salles dont l’utilisateur est responsable.</span><span class="sxs-lookup"><span data-stu-id="ca499-172">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="ca499-173">Le client de conversation permanente obtient la liste des salles suivies à partir du document « présence », où chaque salle de suivi est représentée par une catégorie « roomSetting ».</span><span class="sxs-lookup"><span data-stu-id="ca499-173">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="ca499-174">L’accès à toutes les salles suivies se fait par le biais d’une commande unique SIP INFO qui contient la commande XCCOS **bjoin**, qui elle-même contient la liste d’URI des salles.</span><span class="sxs-lookup"><span data-stu-id="ca499-174">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="ca499-175">La liste des salles suivies étant conservée sur le serveur, les clients des ordinateurs ont tous la même liste de salles suivies correspondant l’URI utilisateur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ca499-175">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="ca499-176">Le client de conversation permanente conserve également la liste des salles ouvertes (si cette option est activée par l’utilisateur) dans le registre de l’ordinateur local, puis joint chacune de ces salles lors de la connexion en envoyant un message INFO SIP contenant la commande XCCOS **join** pour chaque salle ouverte.</span><span class="sxs-lookup"><span data-stu-id="ca499-176">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="ca499-177">Cette liste étant conservée dans le registre, elle peut être différente sur deux clients de conversation permanente exécutés sur des ordinateurs différents.</span><span class="sxs-lookup"><span data-stu-id="ca499-177">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="ca499-178">Pour chaque salle jointe, le client de conversation permanente envoie un message d’informations SIP contenant la commande XCCOS **bccontext** .</span><span class="sxs-lookup"><span data-stu-id="ca499-178">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="ca499-179">Le serveur de conversation permanente répond avec un nouveau message d’informations SIP contenant le message de conversation le plus récent dans la salle.</span><span class="sxs-lookup"><span data-stu-id="ca499-179">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="ca499-180">Le client de conversation permanente envoie un message d’informations SIP contenant une commande XCCOS **getinv** (Get invitation) pour demander les nouvelles invitations de salle que le client n’a pas encore vues.</span><span class="sxs-lookup"><span data-stu-id="ca499-180">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="ca499-181">Dans un message d’informations SIP distinct, le serveur de conversation permanente renvoie une liste de ces salles.</span><span class="sxs-lookup"><span data-stu-id="ca499-181">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="ca499-182">S’inscrire à une salle et publier un message</span><span class="sxs-lookup"><span data-stu-id="ca499-182">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="ca499-183">Le diagramme de flux d’appels et les étapes suivants décrivent un scénario classique d’abonnement à une salle et de publication de messages.</span><span class="sxs-lookup"><span data-stu-id="ca499-183">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="ca499-184">**Flux d’appels de salle de conversation permanente et de publication de messages**</span><span class="sxs-lookup"><span data-stu-id="ca499-184">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="ca499-185">![Scénario d’abonnement à une salle et de publication de messages.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Scénario d’abonnement à une salle et de publication de messages.")</span><span class="sxs-lookup"><span data-stu-id="ca499-185">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="ca499-186">À partir du client de conversation permanente, utilisateur1 clique sur **rejoindre une salle de conversation**, clique sur **Rechercher**, puis entre certains critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="ca499-186">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="ca499-187">Le client de conversation permanente envoie un message d’informations SIP contenant la commande XCCOS **chansrch** (recherche de salle), ainsi que les critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="ca499-187">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="ca499-188">Le serveur de conversation permanente interroge la base de données principale et les réponses dans un nouveau message d’informations SIP contenant une liste des salles disponibles qui répondent aux critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="ca499-188">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="ca499-189">L’utilisateur 1 sélectionne la salle de conversation qu’il souhaite rejoindre et clique sur **Suivre cette salle**.</span><span class="sxs-lookup"><span data-stu-id="ca499-189">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="ca499-190">Le client de conversation permanente envoie un message d’information SIP à un serveur de conversation permanente contenant la commande XCCOS **join** et l’ID de la salle de conversation sélectionnée par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ca499-190">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="ca499-191">Le serveur de conversation permanente répond avec un message d’informations SIP contenant les données de mise en service.</span><span class="sxs-lookup"><span data-stu-id="ca499-191">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="ca499-192">Le client de conversation permanente envoie un message d’information SIP à un serveur de conversation permanente qui contient la commande XCCOS **bccontext** (contexte de messagerie instantanée).</span><span class="sxs-lookup"><span data-stu-id="ca499-192">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="ca499-193">Le serveur de conversation permanente récupère l’historique de la conversation et le renvoie au client de conversation permanente dans un message d’informations SIP distinct.</span><span class="sxs-lookup"><span data-stu-id="ca499-193">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="ca499-194">À ce stade, l’utilisateur se trouve dans la salle de conversation et est en mesure de participer.</span><span class="sxs-lookup"><span data-stu-id="ca499-194">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="ca499-195">L’utilisateur 1 entre un nouveau message et clique sur **Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="ca499-195">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="ca499-196">Le client de conversation permanente envoie le message à la salle de conversation dans une commande SIP INFO XCCOS **grpchat** .</span><span class="sxs-lookup"><span data-stu-id="ca499-196">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="ca499-197">Le serveur de conversation permanente stocke une copie de ce nouveau message dans la base de données principale de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="ca499-197">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="ca499-198">Le serveur de conversation permanente envoie une copie distincte du message SIP INFO XCCOS **grpchat** à utilisateur2, qui a déjà accédé à la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="ca499-198">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="ca499-199">Flux d’appels de conformité de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ca499-199">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="ca499-200">Le serveur de conversation permanente utilise Message Queuing (également appelé MSMQ) et une base de données de conformité supplémentaire (mgccomp) pour traiter les données de conformité.</span><span class="sxs-lookup"><span data-stu-id="ca499-200">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="ca499-201">À titre d’exemple de la façon dont les événements de conformité sont traités, la séquence d’événements suivante illustre le traitement d’un événement de publication de message.</span><span class="sxs-lookup"><span data-stu-id="ca499-201">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="ca499-202">Un utilisateur publie un message dans une salle.</span><span class="sxs-lookup"><span data-stu-id="ca499-202">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="ca499-203">Le serveur de conversation permanente place les informations relatives à l’événement dans une file d’attente Message Queuing privée.</span><span class="sxs-lookup"><span data-stu-id="ca499-203">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="ca499-204">Le serveur de conformité de conversation permanente lit cet événement à partir de la file d’attente et le place dans la base de données mgccomp pour le traiter ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="ca499-204">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="ca499-205">Régulièrement, le serveur de conformité de conversation permanente traite un ensemble d’événements dans la base de données et les envoie à l’adaptateur de conformité de conversation permanente pour traitement.</span><span class="sxs-lookup"><span data-stu-id="ca499-205">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="ca499-206">Si l’adaptateur traite correctement les données, le serveur de conformité de conversation permanente supprime les événements de la base de données mgccomp.</span><span class="sxs-lookup"><span data-stu-id="ca499-206">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

