---
title: 'Lync Server 2013: sauvegarder des bases de données de conversation persistante'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8ffb99effcf0a42bbddefd7151aa40a8d691d9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="a9846-102">Sauvegarder des bases de données de chat permanent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9846-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9846-103">_**Dernière modification de la rubrique:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="a9846-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="a9846-104">Le contenu d’une salle de conversation permanente est stocké dans la base de données de chat permanent (MGC. mdf).</span><span class="sxs-lookup"><span data-stu-id="a9846-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="a9846-105">Il s’agit de données vitales qui doivent être sauvegardées régulièrement.</span><span class="sxs-lookup"><span data-stu-id="a9846-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="a9846-106">Outre le contenu d’une salle de conversation, la base de données de conversation permanente stocke également des informations sur les principaux (par exemple, les utilisateurs et les groupes d’utilisateurs), ainsi que les rôles et l’accès à des salles de conversation et des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="a9846-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="a9846-107">Il existe deux méthodes pour sauvegarder les données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="a9846-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="a9846-108">Sauvegarde SQL Server</span><span class="sxs-lookup"><span data-stu-id="a9846-108">SQL Server Backup</span></span>

  - <span data-ttu-id="a9846-109">L' `Export-CsPersistentChatData` applet de passe qui exporte les données de conversation permanente en tant que fichier</span><span class="sxs-lookup"><span data-stu-id="a9846-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="a9846-110">Les données qui sont créées à l’aide de la sauvegarde SQL Server nécessitent considérablement plus d’espace disque, ce qui peut être `Export-CsPersistentChatData`plus de 20 fois plus important que ce qui est créé par la sauvegarde SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a9846-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

