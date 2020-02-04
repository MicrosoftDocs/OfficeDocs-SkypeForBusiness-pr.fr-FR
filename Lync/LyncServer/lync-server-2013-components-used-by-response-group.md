---
title: 'Lync Server 2013 : Composants utilisés par Response Group'
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
ms.openlocfilehash: 81275ca027971d661d3323fbfc175c51d4f4d7d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="c1deb-102">Composants utilisés par Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1deb-102">Components used by Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1deb-103">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="c1deb-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="c1deb-104">L’application Response Group est activée automatiquement lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c1deb-104">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c1deb-105">Cette section décrit les composants qui prennent en charge l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="c1deb-105">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="c1deb-106">Composants de Response Group</span><span class="sxs-lookup"><span data-stu-id="c1deb-106">Response Group Components</span></span>

<span data-ttu-id="c1deb-107">Les composants Microsoft Lync Server 2013 suivants prennent en charge l’application Response Group :</span><span class="sxs-lookup"><span data-stu-id="c1deb-107">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="c1deb-108">\*\*\*\*   Le service d’application de service d’application fournit une plateforme de déploiement, d’hébergement et de gestion d’applications de communications unifiées, telles que Response Group.</span><span class="sxs-lookup"><span data-stu-id="c1deb-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="c1deb-109">Le service d’application est automatiquement installé sur chaque serveur frontal d’une grappe frontale et sur tous les serveurs Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="c1deb-109">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="c1deb-110">**Application de Response Group**   l’application Response Group est l’une des applications de communications unifiées hébergées par le service d’application.</span><span class="sxs-lookup"><span data-stu-id="c1deb-110">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="c1deb-111">Elle est incluse automatiquement lorsque vous déployez Response Group.</span><span class="sxs-lookup"><span data-stu-id="c1deb-111">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="c1deb-112">Le Response Group application route et met en file d’attente les appels entrants vers des groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="c1deb-112">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="c1deb-113">**Module**   linguistique un module linguistique est requis pour la prise en charge de la reconnaissance vocale et de la synthèse vocale.</span><span class="sxs-lookup"><span data-stu-id="c1deb-113">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="c1deb-114">Ces technologies vocales servent lors de la configuration de messages (message de bienvenue et autres messages, ou les questions et réponses du système de réponse vocale interactive, par exemple).</span><span class="sxs-lookup"><span data-stu-id="c1deb-114">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="c1deb-115">Par défaut, les 26 modules linguistiques pris en charge sont installés lors du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1deb-115">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="c1deb-116">**Les fichiers audio sont**utilisés pour les messages et la musique en attente.   </span><span class="sxs-lookup"><span data-stu-id="c1deb-116">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="c1deb-117">\*\*\*\*   Le groupe de réponse du magasin de fichiers utilise le magasin de fichiers pour stocker des fichiers audio.</span><span class="sxs-lookup"><span data-stu-id="c1deb-117">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="c1deb-118">Plusieurs pools de groupe de réponse peuvent utiliser la même instance du magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c1deb-118">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="c1deb-119">**Outil de configuration de Response Group**   l’outil de configuration de Response Group est un outil Web utilisé pour créer et configurer des groupes de réponse.</span><span class="sxs-lookup"><span data-stu-id="c1deb-119">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="c1deb-120">L’outil de configuration de Response Group est inclus dans l’installation des services Web.</span><span class="sxs-lookup"><span data-stu-id="c1deb-120">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="c1deb-121">**Panneau de configuration Microsoft Lync Server 2013**   vous pouvez utiliser le panneau de configuration de Lync Server pour configurer et configurer des groupes d’agents et des files d’attente pour les groupes de réponses.</span><span class="sxs-lookup"><span data-stu-id="c1deb-121">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="c1deb-122">**Lync Server Management Shell**   tous les paramètres de groupe de réponse peuvent être configurés à l’aide d’applets de applet Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c1deb-122">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="c1deb-123">**Microsoft Lync 2013**   -agents officiels (agents nécessaires pour se connecter au groupe avant de pouvoir accepter les appels pour le groupe) utilisez Lync 2013 pour vous connecter et vous déconnecter du groupe.</span><span class="sxs-lookup"><span data-stu-id="c1deb-123">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="c1deb-124">Si un groupe d’agent est configuré pour les agents officiels, les agents cliquent sur un élément de menu dans Lync 2013 pour ouvrir Internet Explorer et afficher une console de pages Web pour se connecter et s’en déconnecter.</span><span class="sxs-lookup"><span data-stu-id="c1deb-124">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="c1deb-125">\*\*\*\*   Les services Web services Web sont requis pour les outils de configuration de Response Group, la console de connexion et de connexion des agents, le panneau de configuration de Lync Server et le service Web du client de Response Group.</span><span class="sxs-lookup"><span data-stu-id="c1deb-125">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="c1deb-126">\*\*\*\*   Response Group Response service Web application de Response Group fournit un service Web client qui peut être utilisé par des applications tierces pour récupérer des informations sur les agents, l’appartenance aux groupes d’agents, l’état de connexion des agents, le statut des appels pour les groupes et les groupes qui prennent en charge les appels anonymes.</span><span class="sxs-lookup"><span data-stu-id="c1deb-126">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="c1deb-127">Lync 2013 et Lync 2010 attendant utiliser le service Web du client de Response Group pour récupérer la liste des groupes de réponses que les agents peuvent utiliser pour effectuer des appels anonymes.</span><span class="sxs-lookup"><span data-stu-id="c1deb-127">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="c1deb-128">Le service Web client est inclus dans le cadre de l’installation des services Web.</span><span class="sxs-lookup"><span data-stu-id="c1deb-128">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

