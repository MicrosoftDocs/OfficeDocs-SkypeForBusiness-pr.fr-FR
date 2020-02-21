---
title: 'Lync Server 2013 : serveurs Edge audio/vidéo (A/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fce9f00d84465928d942220b1ca2275e59a3817
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="213f9-102">Serveurs Edge audio/vidéo (A/V) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="213f9-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="213f9-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="213f9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="213f9-p101">Le service Edge A/V permet à vos utilisateurs internes (les utilisateurs connectés au réseau de votre organisation) de partager des fichiers audio et vidéo avec des utilisateurs externes (des utilisateurs qui ne sont pas connectés au réseau de votre organisation). Outre les données audio et vidéo, le service Edge A/V fournit également une prise en charge du partage du Bureau et du transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="213f9-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="213f9-p102">La gestion du service Edge A/V s’effectue à l’aide de la configuration de ce service. Ces paramètres vous permettent de gérer la quantité maximale de bande passante à allouer par port et par utilisateur, ainsi que de spécifier la durée pendant laquelle un jeton d’authentification peut être utilisé avant de devoir être renouvelé. Les paramètres de configuration Edge A/V peuvent être appliqués à des sites ou à des serveurs Edge A/V individuels. Lors de la détermination de la collection de paramètres qui sera prioritaire, utilisez le guide suivant :</span><span class="sxs-lookup"><span data-stu-id="213f9-p102">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed. A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers. When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="213f9-109">Les paramètres configurés au niveau du service (c’est-à-dire sur un serveur) prévalent sur tous les autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="213f9-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="213f9-p103">Les paramètres configurés au niveau du site prévalent sur les paramètres configurés au niveau global. Les paramètres au niveau du service, quant à eux, prévalent sur les paramètres au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="213f9-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="213f9-112">Les paramètres au niveau global seront utilisés uniquement si aucun autre paramètre du service n’est configuré sur le serveur et s’il n’existe aucun paramètre pour le site où ce serveur est situé.</span><span class="sxs-lookup"><span data-stu-id="213f9-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="213f9-113">Le service Edge A/V peut uniquement être géré à l’aide de Lync Server PowerShell et des applets de commande CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="213f9-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="213f9-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="213f9-114">In This Section</span></span>

  - [<span data-ttu-id="213f9-115">Renvoyer les informations de configuration du serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="213f9-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="213f9-116">Créer ou modifier une collection de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="213f9-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="213f9-117">Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="213f9-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

