---
title: Gestion de Lync Server 2013, serveur de conversation permanente
description: Gestion de Lync Server 2013, serveur de conversation permanente.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe5306c79c738d61b70c3dd079fb55650e6fdae9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544580"
---
# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="36ce8-103">Gestion de Lync Server 2013, serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="36ce8-103">Managing Lync Server 2013, Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36ce8-104">_**Dernière modification de la rubrique :** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="36ce8-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="36ce8-105">Vous pouvez utiliser Lync Server 2013, le serveur de conversation permanente pour permettre à plusieurs utilisateurs de participer à des conversations dans lesquels ils publient du contenu sur des sujets spécifiques, y compris du texte, des liens et des fichiers.</span><span class="sxs-lookup"><span data-stu-id="36ce8-105">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="36ce8-106">Bien que les utilisateurs puissent communiquer en temps réel pendant une session, le contenu de chaque session est persistant, ce qui signifie qu’il reste disponible après la fin d’une session.</span><span class="sxs-lookup"><span data-stu-id="36ce8-106">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="36ce8-107">Le contenu des salles de conversation permanente se compose principalement de messages de texte courts, bien qu’il puisse inclure des messages plus longs, appelés *Articles*, ainsi que des liens hypertexte, des émoticônes et des documents téléchargés.</span><span class="sxs-lookup"><span data-stu-id="36ce8-107">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36ce8-108">Le chargement et le téléchargement de fichiers ne sont pas pris en charge par le client Lync 2013 ; Toutefois, il est toujours pris en charge par Lync Server 2013, serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="36ce8-108">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="36ce8-109">Le client de conversation de groupe hérité peut publier et afficher des fichiers, mais si la même salle de conversation est accessible via le client Lync 2013, il ne pourra pas accéder aux fichiers.</span><span class="sxs-lookup"><span data-stu-id="36ce8-109">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="36ce8-110">L’accès à une salle de conversation est contrôlé par une liste de membres.</span><span class="sxs-lookup"><span data-stu-id="36ce8-110">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="36ce8-111">L’historique d’une salle de conversation est accessible en totalité à tout membre souhaitant le passer en revue dans un ordre chronologique ou effectuer des recherches en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="36ce8-111">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="36ce8-112">Pour plus d’informations sur l’utilisation du client de conversation permanente, voir [Planning for clients in Lync server 2013](lync-server-2013-planning-for-clients.md) dans la documentation de planification et [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="36ce8-112">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="36ce8-113">Lorsque vous configurez le serveur de conversation permanente pour votre organisation, vous spécifiez la configuration initiale lors du déploiement.</span><span class="sxs-lookup"><span data-stu-id="36ce8-113">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="36ce8-114">Toutefois, il peut arriver que vous souhaitiez modifier la façon dont vous implémentez la prise en charge du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="36ce8-114">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="36ce8-115">Par exemple, vous devrez peut-être configurer la prise en charge et les contrôles du serveur de conversation permanente de manière différente pour une équipe ou un groupe spécifique au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="36ce8-115">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="36ce8-116">Cette section fournit des informations et des procédures pour vous aider à personnaliser votre déploiement de serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="36ce8-116">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="36ce8-117">Pour plus d’informations sur les fonctionnalités que vous pouvez configurer pour le serveur de conversation permanente, voir [définition des exigences de votre organisation pour le serveur de conversation permanente dans Lync server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) dans la documentation de planification et fonctionnement du [serveur de conversation permanente dans Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="36ce8-117">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="36ce8-118">Pour plus d’informations sur le déploiement du serveur de conversation permanente pour Lync Server 2013, voir [Deploying persistent Chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="36ce8-118">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="36ce8-119">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="36ce8-119">In This Section</span></span>

  - [<span data-ttu-id="36ce8-120">Fonctionnement du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36ce8-120">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="36ce8-121">Utilisation de catégories pour administrer le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="36ce8-121">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="36ce8-122">Présentation de l’appartenance à la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="36ce8-122">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="36ce8-123">Meilleures pratiques pour le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="36ce8-123">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="36ce8-124">Gestion des catégories, des salles et des compléments dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36ce8-124">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="36ce8-125">Gestion de l’accès des utilisateurs à la conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36ce8-125">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="36ce8-126">Fonctionnement et maintenance du système de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36ce8-126">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

