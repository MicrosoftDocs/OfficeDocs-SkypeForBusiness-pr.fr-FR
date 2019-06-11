---
title: 'Lync Server 2013: fonctionnement du serveur de chat permanent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bf6179e1ce24264c2079b3096fa9bb8c539ca1c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="c02df-102">Fonctionnement du serveur Chat permanent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c02df-102">How Persistent Chat Server works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c02df-103">_**Dernière modification de la rubrique:** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="c02df-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="c02df-104">Lync Server 2013, Lync Chat Server vous permet de participer à des conversations à plusieurs sujets qui persistent dans le temps.</span><span class="sxs-lookup"><span data-stu-id="c02df-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="c02df-105">Le serveur de chat permanent peut aider votre organisation à effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="c02df-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="c02df-106">Amélioration de la communication entre les équipes géographiquement dispersées et celles à plusieurs fonctions</span><span class="sxs-lookup"><span data-stu-id="c02df-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="c02df-107">Élargissement de la sensibilisation et de la participation aux informations</span><span class="sxs-lookup"><span data-stu-id="c02df-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="c02df-108">Améliorer la communication avec votre organisation étendue</span><span class="sxs-lookup"><span data-stu-id="c02df-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="c02df-109">Réduire la surcharge d’information</span><span class="sxs-lookup"><span data-stu-id="c02df-109">Reduce information overload</span></span>

  - <span data-ttu-id="c02df-110">Amélioration de la prise en charge des informations</span><span class="sxs-lookup"><span data-stu-id="c02df-110">Improve information awareness</span></span>

  - <span data-ttu-id="c02df-111">Augmenter la dispersion des connaissances et informations importantes</span><span class="sxs-lookup"><span data-stu-id="c02df-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="c02df-112">Vous pouvez déployer le serveur de chat permanent en tant que rôle facultatif avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c02df-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="c02df-113">Les services de chat permanent s’exécutent sur un pool dédié, et un pool de serveurs de chat permanent dépend d’un pool de serveurs Lync pour router des messages vers ce dernier.</span><span class="sxs-lookup"><span data-stu-id="c02df-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="c02df-114">Les clients utilisent la communication de discussion eXtensible par SIP (XCCOS).</span><span class="sxs-lookup"><span data-stu-id="c02df-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="c02df-115">Les serveurs front-end de Lync Server sont configurés pour acheminer le trafic vers un pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="c02df-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="c02df-116">Architecture de haut niveau</span><span class="sxs-lookup"><span data-stu-id="c02df-116">High-Level Architecture</span></span>

<span data-ttu-id="c02df-117">Les schémas suivants fournissent des perspectives de haut niveau de l’architecture et des services de chat permanent du serveur.</span><span class="sxs-lookup"><span data-stu-id="c02df-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="c02df-118">**Architecture de haut niveau du serveur de conversation permanente**</span><span class="sxs-lookup"><span data-stu-id="c02df-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="c02df-119">![Architecture serveur de chat permanent.] (images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Architecture serveur de chat permanent.")</span><span class="sxs-lookup"><span data-stu-id="c02df-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="c02df-120">**Services de haut niveau du serveur de conversation permanente**</span><span class="sxs-lookup"><span data-stu-id="c02df-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="c02df-121">![Composants serveur de chat permanent.] (images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Composants serveur de chat permanent.")</span><span class="sxs-lookup"><span data-stu-id="c02df-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="c02df-122">Deux services s’exécutent sur les serveurs front-end du serveur Chat permanent:</span><span class="sxs-lookup"><span data-stu-id="c02df-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="c02df-123">Conversation permanente (canal)</span><span class="sxs-lookup"><span data-stu-id="c02df-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="c02df-124">Conformément</span><span class="sxs-lookup"><span data-stu-id="c02df-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="c02df-125">Service de chat permanent (canal)</span><span class="sxs-lookup"><span data-stu-id="c02df-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="c02df-126">Le service de chat permanent (canal) est le principal service responsable du serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="c02df-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="c02df-127">Ce service fournit les fonctions suivantes:</span><span class="sxs-lookup"><span data-stu-id="c02df-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="c02df-128">acceptation des messages entrants ;</span><span class="sxs-lookup"><span data-stu-id="c02df-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="c02df-129">inscription et listage des participants en ligne dans une salle de conversation permanente ;</span><span class="sxs-lookup"><span data-stu-id="c02df-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="c02df-130">retransmission des messages vers les abonnés à d’autres canaux ;</span><span class="sxs-lookup"><span data-stu-id="c02df-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="c02df-131">Implémente la logique pour la gestion des canaux, l’invitation de salle de conversation, la recherche et de nouvelles notifications de contenu</span><span class="sxs-lookup"><span data-stu-id="c02df-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="c02df-132">Le service de chat permanent (canal) stocke et accède au contenu des salles de conversation et aux autres métadonnées système (règles d’autorisation, etc.) à l’aide du magasin permanent de conversation.</span><span class="sxs-lookup"><span data-stu-id="c02df-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="c02df-133">Ce service stocke les fichiers téléchargés dans des salles de conversation dans le magasin de fichiers de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="c02df-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="c02df-134">Service de conformité</span><span class="sxs-lookup"><span data-stu-id="c02df-134">Compliance Service</span></span>

<span data-ttu-id="c02df-135">Le service de conformité est un composant facultatif de chat permanent qui est chargé de l’archivage du contenu et des événements de conversation dans le magasin de conformité des conversations permanentes.</span><span class="sxs-lookup"><span data-stu-id="c02df-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="c02df-136">Si le règlement de votre organisation impose un archivage de l’activité de conversation permanente, vous pouvez déployer le service de conformité de conversation permanente facultatif.</span><span class="sxs-lookup"><span data-stu-id="c02df-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="c02df-137">Le service de conformité est installé sur chaque serveur de chat permanent d’un pool de conversations permanentes.</span><span class="sxs-lookup"><span data-stu-id="c02df-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="c02df-138">Dans le cadre de la configuration, la compatibilité avec le serveur Chat permanent enregistre les activités de l’utilisateur, telles que la participation et le départ des salles, et la publication et la lecture des messages.</span><span class="sxs-lookup"><span data-stu-id="c02df-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="c02df-139">Le service de conformité stocke les fichiers qui doivent être archivés dans le magasin de fichiers de conformité des conversations permanentes.</span><span class="sxs-lookup"><span data-stu-id="c02df-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="c02df-140">Services Web de chat permanent</span><span class="sxs-lookup"><span data-stu-id="c02df-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="c02df-141">Sur les serveurs front-end de Lync Server, deux services s’exécutent en fonction de Internet Information Services (IIS) et sont implémentés en tant que composants Web:</span><span class="sxs-lookup"><span data-stu-id="c02df-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="c02df-142">**Services Web de chat permanent pour le chargement et le téléchargement de fichiers** Responsable de la publication et de l’extraction de fichiers de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="c02df-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="c02df-143">**Services Web de chat permanent pour la gestion des salles de conversation** Responsable d’offrir aux utilisateurs la possibilité de gérer leurs salles de conversation et de créer des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="c02df-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="c02df-144">Comment puis-je commencer à utiliser le serveur de chat permanent?</span><span class="sxs-lookup"><span data-stu-id="c02df-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="c02df-145">Le serveur Chat permanent est un rôle serveur facultatif au sein de l’infrastructure 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c02df-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="c02df-146">Si vous installez le rôle serveur Chat permanent, tous les utilisateurs qui ont été activés par l’intermédiaire de la stratégie par un administrateur peuvent utiliser la conversation permanente avec le client 2013 Lync.</span><span class="sxs-lookup"><span data-stu-id="c02df-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="c02df-147">Pour plus d’informations sur le déploiement d’un serveur de chat permanent et permettre aux utilisateurs de tirer parti des fonctionnalités d’une stratégie, voir [déploiement d’un serveur de chat permanent dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="c02df-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="c02df-148">Pour plus d’informations sur la configuration des paramètres du déploiement de votre serveur Chat permanent, voir [déploiement d’un serveur de chat permanent dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) et [gestion de Lync Server 2013, serveur de chat permanent](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="c02df-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="c02df-149">Pour plus d’informations sur la façon d’activer les utilisateurs par stratégie de telle sorte qu’ils puissent tirer parti de la fonctionnalité de conversation persistante dans le client Lync 2013, voir [déploiement d’un serveur de chat permanent dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) et [gestion de Lync Server 2013, serveur de chat permanent](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="c02df-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="c02df-150">Pour plus d’informations sur la configuration des paramètres de conformité, reportez-vous à la section [gestion de Lync server 2013, serveur de chat permanent](managing-lync-server-2013-persistent-chat-server.md) .</span><span class="sxs-lookup"><span data-stu-id="c02df-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="c02df-151">Flux d’appels permanents de conversation</span><span class="sxs-lookup"><span data-stu-id="c02df-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="c02df-152">Le client de chat permanent communique avec le service de chat permanent à l’aide de XCCOS.</span><span class="sxs-lookup"><span data-stu-id="c02df-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="c02df-153">Les séquences suivantes décrivent le processus de connexion et un scénario standard d’abonnement de salle et de publication de message.</span><span class="sxs-lookup"><span data-stu-id="c02df-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="c02df-154">Connexion</span><span class="sxs-lookup"><span data-stu-id="c02df-154">Sign-in</span></span>

<span data-ttu-id="c02df-155">Le diagramme de flux d’appels et les étapes suivants décrivent le processus de connexion.</span><span class="sxs-lookup"><span data-stu-id="c02df-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="c02df-156">**Flux d’appels de connexion permanent du client de conversation**</span><span class="sxs-lookup"><span data-stu-id="c02df-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="c02df-157">![Diagramme de flux d’appels de chat permanent du serveur.] (images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagramme de flux d’appels de chat permanent du serveur.")</span><span class="sxs-lookup"><span data-stu-id="c02df-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="c02df-158">Le client de chat permanent envoie d’abord un abonnement SIP pour extraire le document de mise en service intrabande du serveur.</span><span class="sxs-lookup"><span data-stu-id="c02df-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="c02df-159">Ce document indique si la conversation permanente est activée ou désactivée pour l’utilisateur et la liste des URI SIP pour le pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="c02df-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="c02df-160">Le client de chat permanent envoie un message d’invitation SIP à l’URI SIP du serveur de chat permanent qu’il a obtenu lors de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="c02df-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="c02df-161">La séquence d’invitation est suivie de 200 OK et ACK, et le client chat permanent a ouvert une session SIP avec un point de terminaison de serveur Chat permanent.</span><span class="sxs-lookup"><span data-stu-id="c02df-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="c02df-162">Par conséquent, le client de chat permanent communique avec le serveur de chat permanent en envoyant des messages d’informations SIP contenant des messages de discussion ou des commandes demandant au serveur d’effectuer une action.</span><span class="sxs-lookup"><span data-stu-id="c02df-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="c02df-163">Tous ces messages sont reconnus par l’utilisation de 200 OK ou d' 503 Service indisponible (autrement dit, en cas de charge importante du serveur).</span><span class="sxs-lookup"><span data-stu-id="c02df-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="c02df-164">Si le client reçoit une réponse 503, il tentera de réessayer le message.</span><span class="sxs-lookup"><span data-stu-id="c02df-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="c02df-165">(Cet exemple n’inclut pas de réponse 503.) Si le serveur accepte le message ou la commande et envoie 200 OK, il fournit une réponse au client sous la forme d’un message d’INFO SIP distinct.</span><span class="sxs-lookup"><span data-stu-id="c02df-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="c02df-166">Cette réponse inclut une référence à la commande d’origine.</span><span class="sxs-lookup"><span data-stu-id="c02df-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="c02df-167">Le client de chat permanent envoie un message d’information SIP contenant la commande XCCOS **GetServerInfo** .</span><span class="sxs-lookup"><span data-stu-id="c02df-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="c02df-168">Le serveur Chat permanent répond avec un nouveau message SIP INFO contenant des informations sur la configuration du service de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="c02df-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="c02df-169">Le client de chat permanent envoie un message d’information SIP contenant la commande XCCOS **GetAssociations** .</span><span class="sxs-lookup"><span data-stu-id="c02df-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="c02df-170">Le serveur Chat permanent répond avec un nouveau message SIP INFO qui contient la liste des salles dont l’utilisateur est membre.</span><span class="sxs-lookup"><span data-stu-id="c02df-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="c02df-171">Le client de chat permanent répète la commande pour récupérer la liste des salles dont il est le gestionnaire.</span><span class="sxs-lookup"><span data-stu-id="c02df-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="c02df-172">Le client de chat permanent obtient la liste des salles suivies du document «présence», où chaque salle suivie est représentée par une catégorie «roomSetting».</span><span class="sxs-lookup"><span data-stu-id="c02df-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="c02df-173">Toutes les salles suivies sont jointes à l’aide d’un seul message SIP INFO contenant la commande XCCOS **bPour y accéder** qui contient la liste des URI de la salle.</span><span class="sxs-lookup"><span data-stu-id="c02df-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="c02df-174">Dans la mesure où la liste des salles suivies est conservée sur le serveur, tous les clients sur n’importe quel ordinateur disposent de la même liste de salles suivies pour l’URI de l’utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="c02df-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="c02df-175">Le client de chat permanent conserve également la liste des salles ouvertes (si cette option est activée par l’utilisateur) dans le registre de l’ordinateur local et joint chacune de ces pièces lors de la connexion en envoyant un message SIP INFO contenant la commande XCCOS **join** de chaque salle ouverte. .</span><span class="sxs-lookup"><span data-stu-id="c02df-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="c02df-176">Dans la mesure où cette liste est conservée dans le registre, elle peut être différente sur deux clients de chat permanent s’exécutant sur des ordinateurs différents.</span><span class="sxs-lookup"><span data-stu-id="c02df-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="c02df-177">Pour chaque salle jointe, le client de chat permanent envoie un message d’information SIP contenant la commande XCCOS **bccontext** .</span><span class="sxs-lookup"><span data-stu-id="c02df-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="c02df-178">Le serveur Chat permanent répond avec un nouveau message SIP INFO contenant le message de conversation le plus récent dans la salle.</span><span class="sxs-lookup"><span data-stu-id="c02df-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="c02df-179">Le client de chat permanent envoie un message d’information SIP contenant une commande XCCOS **getinv** (qui est une invitation) pour demander toute nouvelle invitation de salle que le client n’a pas encore détectée.</span><span class="sxs-lookup"><span data-stu-id="c02df-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="c02df-180">Dans un message des informations SIP distinctes, le serveur de chat permanent renvoie une liste de ces salles.</span><span class="sxs-lookup"><span data-stu-id="c02df-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="c02df-181">S’abonner à une salle et publier un message</span><span class="sxs-lookup"><span data-stu-id="c02df-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="c02df-182">Le schéma de flux d’appels et les étapes suivants décrivent un scénario type d’abonnement de salle et de publication de message.</span><span class="sxs-lookup"><span data-stu-id="c02df-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="c02df-183">**Flux d’abonnement d’une salle de conversation permanente et flux d’appels de publication de message**</span><span class="sxs-lookup"><span data-stu-id="c02df-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="c02df-184">![Scénario d’abonnement de salle et de publication de message.] (images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Scénario d’abonnement de salle et de publication de message.")</span><span class="sxs-lookup"><span data-stu-id="c02df-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="c02df-185">À partir du client de chat permanent, User1 clique sur **rejoindre une salle de conversation**, clique sur **Rechercher**, puis saisit des critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="c02df-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="c02df-186">Le client de chat permanent envoie un message d’information SIP contenant la commande XCCOS **chansrch** (recherche de salle), ainsi que les critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="c02df-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="c02df-187">Le serveur Chat permanent interroge la base de données principale et les réponses dans un nouveau message SIP INFO contenant une liste des salles disponibles qui répondent aux critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="c02df-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="c02df-188">User1 sélectionne la salle de conversation à laquelle il souhaite participer, puis clique sur **suivre cette salle**.</span><span class="sxs-lookup"><span data-stu-id="c02df-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="c02df-189">Le client de chat permanent envoie un message de chat permanent contenant la commande de **jointure** XCCOS et l’ID de la salle de conversation sélectionnée par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c02df-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="c02df-190">Le serveur Chat permanent répond avec un message SIP INFO contenant les données de mise en service.</span><span class="sxs-lookup"><span data-stu-id="c02df-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="c02df-191">Le client de chat permanent envoie un message de chat permanent contenant le message SIP ( \*\*\*\* contexte de conversation).</span><span class="sxs-lookup"><span data-stu-id="c02df-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="c02df-192">Le serveur Chat permanent récupère l’historique de la discussion et la renvoie au client de chat permanent dans un message d’informations SIP distinct.</span><span class="sxs-lookup"><span data-stu-id="c02df-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="c02df-193">À ce stade, l’utilisateur entre dans la salle de conversation et est prêt à participer.</span><span class="sxs-lookup"><span data-stu-id="c02df-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="c02df-194">User1 entre un nouveau message, puis clique sur **Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="c02df-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="c02df-195">Le client chat permanent publie le message dans la salle de conversation à l’invite SIP INFO XCCOS **grpchat** .</span><span class="sxs-lookup"><span data-stu-id="c02df-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="c02df-196">Le serveur Chat permanent enregistre une copie de ce nouveau message dans la base de données principale de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="c02df-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="c02df-197">Serveur Chat permanent envoie une copie distincte du message SIP INFO XCCOS **grpchat** message à utilisateur2, qui a déjà entré la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="c02df-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="c02df-198">Flux d’appels permanents de conformité des conversations</span><span class="sxs-lookup"><span data-stu-id="c02df-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="c02df-199">Le serveur Chat permanent utilise Message Queuing (également connu sous le nom de MSMQ) ainsi qu’une base de données de conformité supplémentaire (mgccomp) pour traiter les données de conformité.</span><span class="sxs-lookup"><span data-stu-id="c02df-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="c02df-200">Pour illustrer le traitement des événements de conformité, la séquence d’événements suivante décrit le traitement d’un événement de publication de message.</span><span class="sxs-lookup"><span data-stu-id="c02df-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="c02df-201">Un utilisateur publie un message dans une salle.</span><span class="sxs-lookup"><span data-stu-id="c02df-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="c02df-202">Serveur Chat permanent place les informations relatives à l’événement dans une file d’attente de Message Queuing privée.</span><span class="sxs-lookup"><span data-stu-id="c02df-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="c02df-203">Le serveur de conformité des conversations permanent lit cet événement à partir de la file d’attente, puis le place dans la base de données mgccomp pour le traitement.</span><span class="sxs-lookup"><span data-stu-id="c02df-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="c02df-204">Périodiquement, le serveur de conformité des conversations persistantes traite un ensemble d’événements dans la base de données et les envoie à l’adaptateur de conformité de la conversation permanente pour le traitement.</span><span class="sxs-lookup"><span data-stu-id="c02df-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="c02df-205">Si la carte traite correctement les données, le serveur de conformité des conversations permanentes supprime les événements de la base de données mgccomp.</span><span class="sxs-lookup"><span data-stu-id="c02df-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

