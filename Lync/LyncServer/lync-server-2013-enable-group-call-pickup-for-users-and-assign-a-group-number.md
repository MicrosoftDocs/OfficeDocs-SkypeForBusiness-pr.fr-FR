---
title: 'Lync Server 2013 : activation de la prise d’appel de groupe pour les utilisateurs et attribution d’un numéro de groupe'
description: 'Lync Server 2013 : activer la prise d’appel de groupe pour les utilisateurs et attribuer un numéro de groupe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a03fcb20bfd88842dc8b29100b9ece595bf76254
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559640"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="1df5a-103">Activer la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013 et affecter un numéro de groupe</span><span class="sxs-lookup"><span data-stu-id="1df5a-103">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1df5a-104">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="1df5a-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="1df5a-105">Une fois que vous avez ajouté des numéros de groupe de prise d’appel à la table d’orbites de parcage d’appel, vous affectez les numéros de groupe aux utilisateurs et activez la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="1df5a-105">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="1df5a-106">Utilisez l’outil de kit de ressources de fonctionnalité d’extension secondaire (SEFAUtil) pour affecter des numéros de groupe et activer la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="1df5a-106">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1df5a-107">Dans un déploiement hybride, n’affectez pas un groupe de prise d’appel de groupe aux utilisateurs hébergés en ligne.</span><span class="sxs-lookup"><span data-stu-id="1df5a-107">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="1df5a-108">Les utilisateurs hébergés en ligne ne peuvent pas participer à la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="1df5a-108">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="1df5a-109">Autrement dit, leurs appels ne peuvent pas être traités par d’autres utilisateurs, et ils ne peuvent pas répondre aux appels à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1df5a-109">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="1df5a-110">Pour affecter un numéro de groupe et activer la prise d’appel de groupe pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="1df5a-110">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="1df5a-111">Ouvrez une session sur l’ordinateur sur lequel vous avez installé l’outil SEFAUtil avec des droits d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="1df5a-111">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="1df5a-112">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1df5a-112">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="1df5a-113">Par exemple, pour attribuer le numéro de groupe 199 à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="1df5a-113">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1df5a-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1df5a-114">See Also</span></span>


[<span data-ttu-id="1df5a-115">Désactivation de la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1df5a-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

