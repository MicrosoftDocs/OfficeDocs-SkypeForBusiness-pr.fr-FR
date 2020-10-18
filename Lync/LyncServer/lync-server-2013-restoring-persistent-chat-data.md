---
title: 'Lync Server 2013 : restauration des données de conversation permanente'
description: 'Lync Server 2013 : restauration des données de conversation permanente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c75683e151daaadab8374ed5b41886da9a3aea3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575514"
---
# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="19be0-103">Restauration des données de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19be0-103">Restoring Persistent Chat data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19be0-104">_**Dernière modification de la rubrique :** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="19be0-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="19be0-105">Le contenu de la salle de conversation permanente est stocké dans la base de données de conversation permanente (MGC. mdf).</span><span class="sxs-lookup"><span data-stu-id="19be0-105">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="19be0-106">Il s’agit de données stratégiques qui doivent être sauvegardées régulièrement.</span><span class="sxs-lookup"><span data-stu-id="19be0-106">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="19be0-107">En plus du contenu de la salle de conversation, les principaux (tels que les utilisateurs et les groupes), ainsi que les rôles et l’accès dont ils disposent aux salles de conversation et au contenu de la salle de conversation, sont également stockés dans la base de données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="19be0-107">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="19be0-108">La manière dont vous restaurez vos données de conversation permanente dépend de la méthode que vous avez utilisée pour la sauvegarder.</span><span class="sxs-lookup"><span data-stu-id="19be0-108">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="19be0-109">Si vous avez utilisé les procédures de sauvegarde SQL Server, vous devez utiliser les procédures de restauration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="19be0-109">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="19be0-110">Si vous avez utilisé l’applet de commande **Export-applet cspersistentchatdata** pour sauvegarder les données de conversation permanente, vous devez utiliser l’applet de commande **Import-applet cspersistentchatdata** pour restaurer les données.</span><span class="sxs-lookup"><span data-stu-id="19be0-110">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

