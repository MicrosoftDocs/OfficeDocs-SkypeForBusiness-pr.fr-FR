---
title: 'Lync Server 2013 : affectation de numéros de prise d’appel de groupe aux utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ced3de74542edc65de68ab5f803934aa671575cc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499481"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="17bc1-102">Affecter des numéros de prise d’appel de groupe aux utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17bc1-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17bc1-103">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="17bc1-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="17bc1-104">Une fois que vous avez ajouté les numéros de groupe de prise d’appel de groupe à la table des orbites de parcage d’appel, vous pouvez affecter les groupes aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="17bc1-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="17bc1-105">Utilisez l’outil de kit de ressources de fonctionnalité d’extension secondaire (SEFAUtil) pour affecter des groupes de prise d’appel aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="17bc1-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17bc1-106">Dans un déploiement hybride, n’affectez pas un groupe de prise d’appel de groupe aux utilisateurs hébergés en ligne.</span><span class="sxs-lookup"><span data-stu-id="17bc1-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="17bc1-107">Les utilisateurs hébergés en ligne ne peuvent pas participer à la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="17bc1-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="17bc1-108">Autrement dit, leurs appels ne peuvent pas être traités par d’autres utilisateurs, et ils ne peuvent pas répondre aux appels à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="17bc1-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="17bc1-109">Pour affecter un groupe de prise d’appel de groupe à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="17bc1-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="17bc1-110">Ouvrez une session sur l’ordinateur sur lequel vous avez installé l’outil SEFAUtil avec des droits d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="17bc1-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="17bc1-111">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="17bc1-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="17bc1-112">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="17bc1-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17bc1-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17bc1-113">See Also</span></span>


[<span data-ttu-id="17bc1-114">Activer la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17bc1-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="17bc1-115">Désactivation de la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17bc1-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

