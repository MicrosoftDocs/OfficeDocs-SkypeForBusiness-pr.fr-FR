---
title: 'Lync Server 2013 : configuration du serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21c43bfaf3b40a746f09a000cb089509b589e39e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="6a822-102">Configurer le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a822-102">Configure Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a822-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="6a822-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="6a822-104">Pour créer une nouvelle configuration de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6a822-104">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="6a822-105">Pour obtenir une configuration de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6a822-105">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="6a822-106">Pour supprimer la configuration de la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6a822-106">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="6a822-107">Pour définir la configuration de la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6a822-107">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="6a822-108">Pour Lync Server 2013, tout le trafic de service Web est pris en charge sur les serveurs Lync Server 2013, frontaux.</span><span class="sxs-lookup"><span data-stu-id="6a822-108">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="6a822-109">Par conséquent, l’adresse gcweb01 sur le serveur de conversation permanente n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6a822-109">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="6a822-110">Nous prenons toujours en charge l’accès au service web interne, car nous fournissons le service web de transfert/téléchargement de fichiers sur le site web *interne* uniquement (pas sur le site web *externe* pour les utilisateurs distants).</span><span class="sxs-lookup"><span data-stu-id="6a822-110">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

