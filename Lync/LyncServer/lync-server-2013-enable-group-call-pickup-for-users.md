---
title: 'Lync Server 2013 : activation de la prise d’appel de groupe pour les utilisateurs'
description: 'Lync Server 2013 : activation de la prise d’appel de groupe pour les utilisateurs.'
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
ms.openlocfilehash: 27951e9000fd17aac90339cf2a507757ae96a397
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559620"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="36ccf-103">Activer la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36ccf-103">Enable Group Call Pickup for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36ccf-104">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="36ccf-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="36ccf-105">Utilisez l’outil Kit de ressources SEFAUtil pour activer la prise d’appel de groupe pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="36ccf-105">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="36ccf-106">Les utilisateurs doivent se voir attribuer un numéro de groupe avec le type GroupPickup dans la table des orbites de parcage d’appel pour activer la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="36ccf-106">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="36ccf-107">Vous pouvez attribuer un numéro de groupe de prise d’appel et activer la prise d’appel de groupe en même temps à l’aide du paramètre/enablegrouppickup lorsque vous exécutez SEFAUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="36ccf-107">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="36ccf-108">Pour activer la prise d’appel de groupe pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="36ccf-108">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="36ccf-109">Ouvrez une session sur l’ordinateur sur lequel vous avez installé l’outil SEFAUtil avec des droits d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="36ccf-109">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="36ccf-110">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="36ccf-110">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="36ccf-111">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="36ccf-111">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36ccf-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="36ccf-112">See Also</span></span>


[<span data-ttu-id="36ccf-113">Affecter des numéros de prise d’appel de groupe aux utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36ccf-113">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="36ccf-114">Désactivation de la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36ccf-114">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

