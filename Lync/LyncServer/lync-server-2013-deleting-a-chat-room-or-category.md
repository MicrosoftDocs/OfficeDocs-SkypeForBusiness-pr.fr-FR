---
title: 'Lync Server 2013 : suppression d’une catégorie ou d’une salle de conversation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e94068337747feee592ec25669e9d7b5fc10bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="29b56-102">Suppression d’une salle de conversation ou d’une catégorie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29b56-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29b56-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="29b56-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="29b56-104">Les salles de conversation permanente peuvent être supprimées.</span><span class="sxs-lookup"><span data-stu-id="29b56-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="29b56-105">Si vous disposez d’une salle de conversation qui n’est plus utilisée, vous pouvez la désactiver.</span><span class="sxs-lookup"><span data-stu-id="29b56-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="29b56-106">Pour plus d’informations, reportez-vous à [la rubrique désactivation ou activation d’une salle de conversation dans Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span><span class="sxs-lookup"><span data-stu-id="29b56-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="29b56-107">Un administrateur de conversation permanente peut rechercher des salles de conversation désactivées et peut régulièrement purger et supprimer définitivement les salles de conversation à l’aide de l’applet de commande Windows PowerShell, **Remove-applet cspersistentchatroom**.</span><span class="sxs-lookup"><span data-stu-id="29b56-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="29b56-108">Les catégories peuvent être supprimées.</span><span class="sxs-lookup"><span data-stu-id="29b56-108">Categories can be deleted.</span></span> <span data-ttu-id="29b56-109">Toutefois, pour supprimer une catégorie, vous devez d’abord soit supprimer les salles de conversation subordonnées, soit déplacer toutes les salles de conversation vers une autre catégorie, ce qui laisse une catégorie vide pour permettre sa suppression.</span><span class="sxs-lookup"><span data-stu-id="29b56-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="29b56-110">Le serveur de conversation permanente ne vous permet pas de supprimer une catégorie contenant des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="29b56-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="29b56-111">Pour plus d’informations, reportez-vous à [la rubrique migration d’une salle de conversation d’une catégorie vers une autre dans Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span><span class="sxs-lookup"><span data-stu-id="29b56-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="29b56-112">Pour plus d’informations sur la suppression de catégories vides à l’aide de l’interface de ligne de commande Windows PowerShell, voir « gestion des salles » dans [Configuring persistent Chat Server by Using Windows PowerShell Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="29b56-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="29b56-113">Pour plus d’informations sur les salles de conversation et les catégories, voir [configure rooms in Lync server 2013](lync-server-2013-configure-rooms.md) et [configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="29b56-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

