---
title: 'Lync Server 2013 : Vue d’ensemble du serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a744f4eb251bbbacc8b1b5f4c2a5978a9689f225
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="8858f-102">Vue d’ensemble du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8858f-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8858f-103">_**Dernière modification de la rubrique:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="8858f-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="8858f-104">Lync Server 2013, serveur de chat permanent permet aux utilisateurs de participer à des conversations à plusieurs sujets qui persistent dans le temps.</span><span class="sxs-lookup"><span data-stu-id="8858f-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="8858f-105">Le serveur de chat permanent peut aider votre organisation à effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="8858f-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="8858f-106">Améliorez la communication entre les équipes géographiquement dispersées et celles à plusieurs fonctions.</span><span class="sxs-lookup"><span data-stu-id="8858f-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="8858f-107">En utilisant la conversation permanente, les équipes peuvent facilement partager des informations, des idées et des décisions entre elles.</span><span class="sxs-lookup"><span data-stu-id="8858f-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="8858f-108">Les messages publiés dans des salles de conversation (forums de discussion) peuvent persister (autrement dit, qui peuvent être disponibles dans le temps), de sorte que les personnes de différents sites et services peuvent participer, même s’ils ne sont pas en ligne simultanément.</span><span class="sxs-lookup"><span data-stu-id="8858f-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="8858f-109">Lorsqu’un utilisateur se connecte à une salle de conversation, la messagerie instantanée (le nombre configurable de messages de l’historique) est automatiquement chargée dans la salle de conversation pour fournir à l’utilisateur un contexte pour la conversation.</span><span class="sxs-lookup"><span data-stu-id="8858f-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="8858f-110">Améliorez la sensibilisation des informations.</span><span class="sxs-lookup"><span data-stu-id="8858f-110">Improve information awareness.</span></span> <span data-ttu-id="8858f-111">En utilisant des filtres côté client, les utilisateurs peuvent définir des conditions (par exemple, des mots-clés dans le contenu d’un message ou la valeur du champ «de» dans un message) pour recevoir une notification quand ces conditions sont remplies dans des messages instantanés ou des salles de conversation persistants.</span><span class="sxs-lookup"><span data-stu-id="8858f-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="8858f-112">De cette façon, les utilisateurs peuvent rester à jour avec le contenu qui les intéressent le plus.</span><span class="sxs-lookup"><span data-stu-id="8858f-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="8858f-113">Améliorer la communication avec son organisation étendue.</span><span class="sxs-lookup"><span data-stu-id="8858f-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="8858f-114">En facilitant la collaboration sur des sujets de longue durée avec d’autres personnes au sein de l’organisation et en fournissant un emplacement permanent pour partager les informations, la conversation permanente contribue à améliorer la communication.</span><span class="sxs-lookup"><span data-stu-id="8858f-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="8858f-115">Réduire la surcharge des informations.</span><span class="sxs-lookup"><span data-stu-id="8858f-115">Reduce information overload.</span></span> <span data-ttu-id="8858f-116">Les utilisateurs peuvent suivre des salles de conversation et des messages particulièrement intéressants en utilisant des filtres côté client et ajouter des salles de conversation que vous voulez suivre à leur liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="8858f-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="8858f-117">Augmenter la dispersion des connaissances et informations importantes.</span><span class="sxs-lookup"><span data-stu-id="8858f-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="8858f-118">Les documents et les liens peuvent être inclus dans les conversations, pour que tous les membres puissent y accéder.</span><span class="sxs-lookup"><span data-stu-id="8858f-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="8858f-119">La publication de questions destinées à une équipe plus large permet aux utilisateurs de répondre à des questions d’experts.</span><span class="sxs-lookup"><span data-stu-id="8858f-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="8858f-120">L’intégration avec d’autres systèmes d’information permet de communiquer facilement des données d’entreprise importantes aux grands groupes.</span><span class="sxs-lookup"><span data-stu-id="8858f-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="8858f-121">Pour activer des salles de conversation dans Lync Server 2013, déployez Lync Server 2013 persistent chat.</span><span class="sxs-lookup"><span data-stu-id="8858f-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="8858f-122">Pour plus d’informations sur l’activation des salles de conversation, voir <http://go.microsoft.com/fwlink/p/?linkid=270945>l’aide de la messagerie instantanée à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="8858f-122">For information about enabling chat rooms, see the Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="8858f-123">Si les utilisateurs sont activés pour Lync Server et que la prise en charge de Lync Server est déployée, les utilisateurs peuvent installer et utiliser Lync 2013 chat permanent pour fournir une prise en charge des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="8858f-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="8858f-124">Si votre organisation est tenue de respecter les règles de conformité, vous pouvez éventuellement déployer le service de conformité des conversations permanentes.</span><span class="sxs-lookup"><span data-stu-id="8858f-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

