---
title: 'Lync Server 2013 : Déplacement d’une salle de conversation d’une catégorie vers une autre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61d20ff1de7437054df36af224293dcdcb61d54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="60c24-102">Déplacement d’une salle de conversation d’une catégorie vers une autre dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60c24-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60c24-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="60c24-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="60c24-104">Nous vous recommandons de ne pas modifier la catégorie d’une salle de conversation permanente après la création de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="60c24-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="60c24-105">Toutefois, si le gestionnaire de la salle de conversation dispose de privilèges de **création** dans une autre catégorie, il peut déplacer la salle d’une catégorie vers une autre.</span><span class="sxs-lookup"><span data-stu-id="60c24-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="60c24-106">La salle n’est pas supprimée et recréée.</span><span class="sxs-lookup"><span data-stu-id="60c24-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="60c24-107">Seule son association dans la base de données est modifiée.</span><span class="sxs-lookup"><span data-stu-id="60c24-107">It is a change of association within the database.</span></span>

<span data-ttu-id="60c24-108">Le changement de catégorie d’une salle de conversation doit être rarement réalisé.</span><span class="sxs-lookup"><span data-stu-id="60c24-108">Changing a chat room category should be done rarely.</span></span> <span data-ttu-id="60c24-109">Une catégorie détermine l’appartenance autorisée pour la salle de conversation, donc si une salle de conversation est déplacée vers une autre catégorie, toutes les listes de contrôle d’accès système (SACL) qui ne sont plus prises en charge par la nouvelle catégorie sont vidées.</span><span class="sxs-lookup"><span data-stu-id="60c24-109">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="60c24-110">Par exemple, si un utilisateur était membre de la salle et n’est plus **AllowedMember** dans la nouvelle catégorie, l’appartenance à la salle sera modifiée et l’utilisateur sera supprimé de la salle.</span><span class="sxs-lookup"><span data-stu-id="60c24-110">For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="60c24-111">Pour plus d’informations sur le déplacement d’une salle de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, reportez-vous à la section «gestion des salles» dans [configuration du serveur de chat permanent à l’aide des cmdlets Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="60c24-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="60c24-112">Pour plus d’informations sur la configuration des salles de conversation, voir [configurer des salles dans Lync Server 2013](lync-server-2013-configure-rooms.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="60c24-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

