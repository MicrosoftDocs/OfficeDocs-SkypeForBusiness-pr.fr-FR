---
title: 'Lync Server 2013 : vue d’ensemble du serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38188067f5320c7e9fc6aa7ccef60812d5a42023
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="a4237-102">Vue d’ensemble du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4237-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4237-103">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="a4237-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="a4237-104">Lync Server 2013, serveur de conversation permanente permet aux utilisateurs de participer à des conversations à plusieurs sujets qui persistent dans le temps.</span><span class="sxs-lookup"><span data-stu-id="a4237-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="a4237-105">Le serveur de conversation permanente peut aider votre organisation à effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4237-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="a4237-106">Améliorer la communication entre des équipes géographiquement dispersées et multifonctionnelles.</span><span class="sxs-lookup"><span data-stu-id="a4237-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="a4237-107">À l’aide de la conversation permanente, les équipes peuvent partager efficacement des informations, des idées et des décisions les uns avec les autres.</span><span class="sxs-lookup"><span data-stu-id="a4237-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="a4237-108">Les messages publiés dans les salles de conversation (forums de discussion) peuvent persister (disponibles dans le temps), afin que les utilisateurs de différents emplacements et services puissent participer, même s’ils ne sont pas en ligne simultanément.</span><span class="sxs-lookup"><span data-stu-id="a4237-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="a4237-109">Lorsqu’un utilisateur se connecte à une salle de conversation, la conversation (un nombre configurable de messages d’historique de conversation) est automatiquement chargée dans la salle de conversation pour fournir à l’utilisateur un contexte pour la conversation.</span><span class="sxs-lookup"><span data-stu-id="a4237-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="a4237-110">Améliorer la prise en compte des informations.</span><span class="sxs-lookup"><span data-stu-id="a4237-110">Improve information awareness.</span></span> <span data-ttu-id="a4237-111">À l’aide de filtres côté client, les utilisateurs peuvent définir des conditions, telles que des mots clés dans le contenu d’un message ou la valeur du champ « de » dans un message, pour recevoir des notifications lorsque ces conditions sont remplies dans les messages instantanés de conversation permanente ou les messages de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="a4237-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="a4237-112">De cette façon, les utilisateurs peuvent rester à jour avec le contenu qui les intéresse le plus.</span><span class="sxs-lookup"><span data-stu-id="a4237-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="a4237-113">Améliorer la communication avec une organisation étendue.</span><span class="sxs-lookup"><span data-stu-id="a4237-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="a4237-114">En facilitant la collaboration sur des sujets de longue durée avec d’autres personnes de l’organisation et en fournissant un emplacement permanent pour partager des informations, la conversation permanente contribue à améliorer la communication.</span><span class="sxs-lookup"><span data-stu-id="a4237-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="a4237-115">Réduire la surcharge d’informations.</span><span class="sxs-lookup"><span data-stu-id="a4237-115">Reduce information overload.</span></span> <span data-ttu-id="a4237-116">Les utilisateurs peuvent suivre les salles de conversation et les messages les plus intéressants en utilisant des filtres côté client, et ajouter des salles de conversation qu’ils souhaitent suivre à leur liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="a4237-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="a4237-117">Augmenter la dispersion des connaissances et informations importantes.</span><span class="sxs-lookup"><span data-stu-id="a4237-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="a4237-118">Il est possible d’inclure des documents et des liens dans des conversations afin que toute l’équipe puisse y accéder.</span><span class="sxs-lookup"><span data-stu-id="a4237-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="a4237-119">En publiant des questions à l’attention d’une équipe plus vaste, les utilisateurs peuvent bénéficier de réponses fournies par des experts du domaine concerné.</span><span class="sxs-lookup"><span data-stu-id="a4237-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="a4237-120">L’intégration à d’autres systèmes d’informations permet de communiquer facilement les données d’entreprise importantes aux grands groupes.</span><span class="sxs-lookup"><span data-stu-id="a4237-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="a4237-121">Pour activer les salles de conversation dans Lync Server 2013, déployez Lync Server 2013 persistent chat.</span><span class="sxs-lookup"><span data-stu-id="a4237-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="a4237-122">Pour plus d’informations sur l’activation des salles de conversation, consultez <https://go.microsoft.com/fwlink/p/?linkid=270945>l’aide de conversation permanente à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="a4237-122">For information about enabling chat rooms, see the Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="a4237-123">Si les utilisateurs sont activés pour Lync Server et que la prise en charge de Lync Server est déployée, les utilisateurs peuvent installer et utiliser Lync 2013 persistent chat pour fournir la prise en charge de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="a4237-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="a4237-124">Si votre organisation est tenue de suivre les réglementations de conformité, vous pouvez déployer le service de conformité de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="a4237-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

