---
title: 'Lync Server 2013 : activation de la prise d’appel de groupe pour les utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7e744f42368cd02b197533b84352f8f0477d848
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="fb4ad-102">Activer la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb4ad-102">Enable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb4ad-103">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="fb4ad-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="fb4ad-104">Utilisez l’outil Kit de ressources SEFAUtil pour activer la prise d’appel de groupe pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fb4ad-104">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="fb4ad-105">Les utilisateurs doivent se voir attribuer un numéro de groupe avec le type GroupPickup dans la table des orbites de parcage d’appel pour activer la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="fb4ad-105">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="fb4ad-106">Vous pouvez attribuer un numéro de groupe de prise d’appel et activer la prise d’appel de groupe en même temps à l’aide du paramètre/enablegrouppickup lorsque vous exécutez SEFAUtil. exe.</span><span class="sxs-lookup"><span data-stu-id="fb4ad-106">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="fb4ad-107">Pour activer la prise d’appel de groupe pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="fb4ad-107">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="fb4ad-108">Ouvrez une session sur l’ordinateur sur lequel vous avez installé l’outil SEFAUtil avec des droits d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="fb4ad-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="fb4ad-109">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="fb4ad-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="fb4ad-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="fb4ad-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb4ad-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb4ad-111">See Also</span></span>


[<span data-ttu-id="fb4ad-112">Affecter des numéros de prise d’appel de groupe aux utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb4ad-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="fb4ad-113">Désactivation de la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb4ad-113">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

