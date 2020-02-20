---
title: 'Lync Server 2013 : sauvegarde des bases de données de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dc1f448c248f80bfcc636c900b6601fda4aa200
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="1e280-102">Sauvegarde de bases de données de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e280-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e280-103">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="1e280-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="1e280-104">Le contenu de la salle de conversation permanente est stocké dans la base de données de conversation permanente (MGC. mdf).</span><span class="sxs-lookup"><span data-stu-id="1e280-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="1e280-105">Il s’agit de données stratégiques qui doivent être sauvegardées régulièrement.</span><span class="sxs-lookup"><span data-stu-id="1e280-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="1e280-106">Outre le contenu de la salle de conversation, la base de données de conversation permanente stocke également des informations sur les principaux (par exemple, les utilisateurs et les groupes d’utilisateurs), ainsi que sur les rôles et l’accès dont ils disposent aux salles de conversation et à la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="1e280-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="1e280-107">Il existe deux manières de sauvegarder les données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="1e280-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="1e280-108">Sauvegarde SQL Server</span><span class="sxs-lookup"><span data-stu-id="1e280-108">SQL Server Backup</span></span>

  - <span data-ttu-id="1e280-109">L' `Export-CsPersistentChatData` applet de commande, qui exporte les données de conversation permanente en tant que fichier</span><span class="sxs-lookup"><span data-stu-id="1e280-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="1e280-110">Les données créées à l’aide de la sauvegarde SQL Server nécessitent beaucoup plus d’espace disque, parfois 20 fois plus, que `Export-CsPersistentChatData`celles créées par, mais la sauvegarde SQL Server est plus susceptible d’être une procédure que les administrateurs connaissent.</span><span class="sxs-lookup"><span data-stu-id="1e280-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

