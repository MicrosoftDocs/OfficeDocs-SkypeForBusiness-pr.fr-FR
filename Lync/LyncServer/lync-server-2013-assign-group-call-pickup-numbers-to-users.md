---
title: 'Lync Server 2013: attribution de numéros de numérotation des appels de groupe aux utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e919b1fb4ee225eba1c5317ff1f3049791075bcc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="7d0b9-102">Attribution de numéros de numérotation des appels de groupe aux utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d0b9-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d0b9-103">_**Dernière modification de la rubrique:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="7d0b9-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="7d0b9-104">Une fois que vous avez ajouté des numéros de groupe de sélection d’appels de groupe à la table d’orbite du parc d’appels, vous pouvez affecter les groupes aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7d0b9-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="7d0b9-105">Utilisez l’outil Kit de ressources de l’extension secondaire (SEFAUtil) pour affecter des groupes de capture d’appel aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7d0b9-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7d0b9-106">Dans un déploiement hybride, n’affectez pas de groupe de collecte d’appels de groupe aux utilisateurs hébergés en ligne.</span><span class="sxs-lookup"><span data-stu-id="7d0b9-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="7d0b9-107">Les utilisateurs hébergés en ligne ne peuvent pas participer à la cueillette du groupe.</span><span class="sxs-lookup"><span data-stu-id="7d0b9-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="7d0b9-108">Autrement dit, leurs appels ne peuvent pas être pris par d’autres utilisateurs et ils ne peuvent pas répondre aux appels destinés à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7d0b9-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="7d0b9-109">Pour affecter un groupe de prélèvement d’appels de groupe à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7d0b9-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="7d0b9-110">Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="7d0b9-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="7d0b9-111">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7d0b9-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="7d0b9-112">Exemple :</span><span class="sxs-lookup"><span data-stu-id="7d0b9-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d0b9-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d0b9-113">See Also</span></span>


[<span data-ttu-id="7d0b9-114">Activer le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d0b9-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="7d0b9-115">Désactiver le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d0b9-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

