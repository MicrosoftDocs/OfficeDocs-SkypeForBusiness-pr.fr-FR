---
title: 'Lync Server 2013 : composants utilisés par Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bfefeabc1c9f64a4f1bf9fa794b269fbdcb0650
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="cbd06-102">Composants utilisés par Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbd06-102">Components used by Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbd06-103">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="cbd06-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="cbd06-104">L’application Response Group est automatiquement activée lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="cbd06-104">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="cbd06-105">Cette section décrit les composants qui prennent en charge l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="cbd06-105">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="cbd06-106">Composants de l’application Response Group</span><span class="sxs-lookup"><span data-stu-id="cbd06-106">Response Group Components</span></span>

<span data-ttu-id="cbd06-107">Les composants Microsoft Lync Server 2013 suivants prennent en charge l’application Response Group :</span><span class="sxs-lookup"><span data-stu-id="cbd06-107">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="cbd06-108">**Application service**   application service fournit une plateforme permettant de déployer, d’héberger et de gérer des applications de communications unifiées, telles que Response Group.</span><span class="sxs-lookup"><span data-stu-id="cbd06-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="cbd06-109">Le service d’application est automatiquement installé sur chaque serveur frontal dans un pool frontal et sur chaque serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cbd06-109">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="cbd06-110">**Application Response Group**   l’application Response Group est l’une des applications de communications unifiées hébergées par le service d’application.</span><span class="sxs-lookup"><span data-stu-id="cbd06-110">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="cbd06-111">Elle est incluse automatiquement lorsque vous déployez Response Group.</span><span class="sxs-lookup"><span data-stu-id="cbd06-111">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="cbd06-112">L’application Response Group achemine et met en file d’attente les appels entrants vers des groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="cbd06-112">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="cbd06-113">**Module**   linguistique un module linguistique est nécessaire pour prendre en charge la reconnaissance vocale et la synthèse vocale.</span><span class="sxs-lookup"><span data-stu-id="cbd06-113">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="cbd06-114">Ces technologies vocales servent lors de la configuration de messages (message de bienvenue et autres messages, ou les questions et réponses d’une réponse vocale interactive, par exemple).</span><span class="sxs-lookup"><span data-stu-id="cbd06-114">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="cbd06-115">Par défaut, les modules linguistiques 26 pris en charge sont installés lorsque vous déployez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbd06-115">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="cbd06-116">**Fichiers audio les**   fichiers audio sont utilisés pour les messages et la musique en attente.</span><span class="sxs-lookup"><span data-stu-id="cbd06-116">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="cbd06-117">\*\*\*\*   Le groupe de réponse de magasin de fichiers utilise le magasin de fichiers pour stocker les fichiers audio.</span><span class="sxs-lookup"><span data-stu-id="cbd06-117">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="cbd06-118">Plusieurs pools de groupes Response Group peuvent utiliser la même instance du magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="cbd06-118">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="cbd06-119">**Outil de configuration Response Group**   l’outil de configuration Response Group est un outil basé sur le Web qui permet de créer et de configurer des groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="cbd06-119">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="cbd06-120">L’outil de configuration Response Group est inclus lors de l’installation des services Web.</span><span class="sxs-lookup"><span data-stu-id="cbd06-120">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="cbd06-121">**Panneau de configuration**   Microsoft Lync Server 2013 vous pouvez utiliser le panneau de configuration Lync Server pour installer et configurer des groupes d’agents et des files d’attente pour les groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="cbd06-121">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="cbd06-122">**Lync Server Management Shell**   les paramètres du groupe Response Group peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cbd06-122">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="cbd06-123">\*\*\*\*   Les agents formels Microsoft Lync 2013 (les agents qui sont requis pour se connecter au groupe avant de pouvoir accepter des appels pour le groupe) utilisent Lync 2013 pour se connecter à ce groupe et s’en déconnecter.</span><span class="sxs-lookup"><span data-stu-id="cbd06-123">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="cbd06-124">Si un groupe d’agents est configuré pour les agents formels, les agents cliquent sur un élément de menu dans Lync 2013 pour ouvrir Internet Explorer et afficher une console Web pour se connecter et se déconnecter du groupe.</span><span class="sxs-lookup"><span data-stu-id="cbd06-124">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="cbd06-125">\*\*\*\* Les services Web des services Web sont requis pour l’outil de configuration de Response Group, la console de connexion et de déconnexion des agents, le panneau de configuration Lync Server et le service Web du client Response Group.   </span><span class="sxs-lookup"><span data-stu-id="cbd06-125">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="cbd06-126">**Le service**   Web du client Response Group application Response Group fournit un service Web client, qui peut être utilisé par des applications tierces pour récupérer des informations sur les agents, l’appartenance à un groupe d’agents, l’état de connexion de l’agent, l’état de l’appel pour les groupes et les groupes qui prennent en charge les appels anonymes.</span><span class="sxs-lookup"><span data-stu-id="cbd06-126">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="cbd06-127">Lync 2013 et Lync 2010 attendant utilisent le service Web du client Response Group pour récupérer la liste des groupes Response Group que les agents peuvent utiliser pour effectuer des appels anonymes.</span><span class="sxs-lookup"><span data-stu-id="cbd06-127">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="cbd06-128">Le service web client est installé avec les services web.</span><span class="sxs-lookup"><span data-stu-id="cbd06-128">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

