---
title: Gestion de Lync Server 2013, serveur de conversation permanente
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
ms.openlocfilehash: 067e24a7e1534e355e39f80b6a3fda90e059be14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="64f0b-102">Gestion de Lync Server 2013, serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="64f0b-102">Managing Lync Server 2013, Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64f0b-103">_**Dernière modification de la rubrique :** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="64f0b-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="64f0b-104">Vous pouvez utiliser Lync Server 2013, serveur de chat permanent pour permettre à plusieurs utilisateurs de participer à des conversations dans lesquelles ils publient et accèdent au contenu de rubriques spécifiques, y compris le texte, les liens et les fichiers.</span><span class="sxs-lookup"><span data-stu-id="64f0b-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="64f0b-105">Bien que les utilisateurs puissent communiquer en temps réel pendant une session, le contenu de chaque session est persistant, ce qui signifie qu’elle reste disponible à la fin de la session.</span><span class="sxs-lookup"><span data-stu-id="64f0b-105">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="64f0b-106">Le contenu des salles de conversation permanente est essentiellement composé de messages de courte durée, même s’il peut inclure de longs messages, désignés sous le nom de *récits*, ainsi que des liens hypertexte, des émoticônes et des documents téléchargés.</span><span class="sxs-lookup"><span data-stu-id="64f0b-106">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64f0b-107">Le chargement et le téléchargement de fichiers ne sont pas pris en charge par le client Lync 2013 ; Néanmoins, il est toujours pris en charge par Lync Server 2013, serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="64f0b-107">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="64f0b-108">Le client de discussion de groupe hérité peut publier et afficher des fichiers, mais si la même salle de conversation est accessible via le client 2013 Lync, il ne pourra pas accéder aux fichiers.</span><span class="sxs-lookup"><span data-stu-id="64f0b-108">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="64f0b-109">L’accès à une salle de conversation est contrôlé par une liste d’appartenance.</span><span class="sxs-lookup"><span data-stu-id="64f0b-109">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="64f0b-110">L’intégralité de l’historique des salles de conversation est disponible à tous les membres pour la vérification chronologique ou la recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="64f0b-110">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="64f0b-111">Pour plus d’informations sur l’utilisation du client de chat permanent, voir [planification pour les clients dans Lync server 2013](lync-server-2013-planning-for-clients.md) dans la documentation de planification et [déploiement de clients et d’appareils dans Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="64f0b-111">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="64f0b-112">Lorsque vous configurez le serveur de chat permanent pour votre organisation, vous spécifiez la configuration initiale lors du déploiement.</span><span class="sxs-lookup"><span data-stu-id="64f0b-112">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="64f0b-113">Toutefois, il peut arriver que vous souhaitiez modifier le mode de mise en œuvre d’une prise en charge du serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="64f0b-113">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="64f0b-114">Par exemple, il est possible que vous deviez configurer une prise en charge et des contrôles permanents du serveur pour une équipe ou un groupe spécifique au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="64f0b-114">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="64f0b-115">Cette section fournit des informations et des procédures pour vous aider à personnaliser le déploiement de votre serveur Chat permanent.</span><span class="sxs-lookup"><span data-stu-id="64f0b-115">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="64f0b-116">Pour plus d’informations sur les fonctionnalités que vous pouvez configurer pour le serveur de chat permanent, reportez-vous à la rubrique [définition des exigences de votre organisation pour le serveur de chat permanent dans Lync server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) dans la documentation de planification et [fonctionnement du serveur Chat permanent dans Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)</span><span class="sxs-lookup"><span data-stu-id="64f0b-116">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="64f0b-117">Pour plus d’informations sur le déploiement d’un serveur de chat permanent pour Lync Server 2013, voir déploiement d’un [serveur de chat permanent dans Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="64f0b-117">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="64f0b-118">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="64f0b-118">In This Section</span></span>

  - [<span data-ttu-id="64f0b-119">Fonctionnement du serveur Chat permanent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64f0b-119">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="64f0b-120">Utilisation des catégories pour administrer le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="64f0b-120">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="64f0b-121">Présentation de l’appartenance aux conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="64f0b-121">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="64f0b-122">Meilleures pratiques liées au serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="64f0b-122">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="64f0b-123">Gestion des catégories, des salles et des compléments dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64f0b-123">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="64f0b-124">Gestion de l’accès des utilisateurs à la conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64f0b-124">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="64f0b-125">Fonctionnement et maintenance du système de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64f0b-125">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

