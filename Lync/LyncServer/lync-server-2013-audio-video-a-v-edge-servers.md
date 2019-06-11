---
title: 'Serveurs Edge Lync Server 2013: audio/vidéo (A/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9738dbb11ce731ac832a5529d2013f3f9b2907
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="90746-102">Serveurs périphériques audio/vidéo (A/V) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90746-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90746-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="90746-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="90746-104">Le service Edge A/V offre aux utilisateurs internes (qui sont connectés à votre réseau d’entreprise) un moyen de partager des fichiers audio et vidéo avec des utilisateurs externes (les utilisateurs qui ne sont pas connectés au réseau de votre organisation).</span><span class="sxs-lookup"><span data-stu-id="90746-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="90746-105">Outre l’audio et la vidéo, le service Edge A/V assure également la prise en charge du partage de bureau et du transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="90746-105">In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="90746-106">Le service Edge A/V est essentiellement géré à l’aide de la configuration A/V Edge. ces paramètres vous permettent de gérer le volume maximal de bande passante à allouer par port et par utilisateur, et de spécifier la durée pendant laquelle il est possible d’utiliser un jeton d’authentification avant le renouvellement du jeton.</span><span class="sxs-lookup"><span data-stu-id="90746-106">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed.</span></span> <span data-ttu-id="90746-107">Les paramètres de configuration de Microsoft Edge peuvent être appliqués à des sites ou à des serveurs Edge A/V individuels.</span><span class="sxs-lookup"><span data-stu-id="90746-107">A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers.</span></span> <span data-ttu-id="90746-108">Lorsque vous déterminez la collection de paramètres qui sera prioritaire, utilisez le guide suivant:</span><span class="sxs-lookup"><span data-stu-id="90746-108">When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="90746-109">Les paramètres configurés au niveau de l’étendue de service (autrement dit, sur un serveur individuel) sont prioritaires sur tout.</span><span class="sxs-lookup"><span data-stu-id="90746-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="90746-110">Les paramètres configurés lors de l’étendue du site sont prioritaires sur les paramètres configurés au niveau de l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="90746-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="90746-111">Toutefois, les paramètres d’étendue de service remplacent également les paramètres d’étendue de site.</span><span class="sxs-lookup"><span data-stu-id="90746-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="90746-112">Les paramètres au niveau de l’étendue globale seront utilisés uniquement s’il n’y a aucun paramètre de service configuré sur le serveur individuel et s’il n’y a aucun paramètre de site pour le site sur lequel se trouve le serveur.</span><span class="sxs-lookup"><span data-stu-id="90746-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="90746-113">Le service Edge A/V peut être géré uniquement à l’aide de Lync Server PowerShell et des cmdlets CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="90746-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="90746-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="90746-114">In This Section</span></span>

  - [<span data-ttu-id="90746-115">Renvoyer des informations de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90746-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="90746-116">Créer ou modifier un ensemble de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90746-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="90746-117">Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90746-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

