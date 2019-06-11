---
title: 'Lync Server 2013: restauration des données de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ed69938186de2aebf6268168e663abcb125ad86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="89dab-102">Restauration de données de conversations permanentes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89dab-102">Restoring Persistent Chat data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89dab-103">_**Dernière modification de la rubrique:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="89dab-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="89dab-104">Le contenu d’une salle de conversation permanente est stocké dans la base de données de chat permanent (MGC. mdf).</span><span class="sxs-lookup"><span data-stu-id="89dab-104">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="89dab-105">Il s’agit de données vitales qui doivent être sauvegardées régulièrement.</span><span class="sxs-lookup"><span data-stu-id="89dab-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="89dab-106">Outre le contenu d’une salle de conversation, les principaux (tels que les utilisateurs et les groupes) ainsi que les rôles et les autorisations qu’ils doivent utiliser pour discuter des salles de conversation et du contenu des salles de conversation, sont également stockés dans la base de données de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="89dab-106">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="89dab-107">Le mode de restauration des données de conversation persistante dépend de la méthode que vous avez utilisée pour les sauvegarder.</span><span class="sxs-lookup"><span data-stu-id="89dab-107">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="89dab-108">Si vous avez utilisé des procédures de sauvegarde SQL Server, vous devez utiliser des procédures de restauration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89dab-108">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="89dab-109">Si vous avez utilisé l’applet de cmdlet **Export-CsPersistentChatData** pour sauvegarder les données de conversation permanente, vous devez utiliser l’applet de passe **Import-CsPersistentChatData** pour restaurer les données.</span><span class="sxs-lookup"><span data-stu-id="89dab-109">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

