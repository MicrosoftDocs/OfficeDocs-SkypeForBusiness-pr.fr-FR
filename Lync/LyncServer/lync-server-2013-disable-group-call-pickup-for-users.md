---
title: 'Lync Server 2013 : désactiver la prise d’appel de groupe pour les utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d30fc0dd317b9de1a5af76c5a3a10734f0877b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529021"
---
# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="c703b-102">Désactivation de la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c703b-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c703b-103">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="c703b-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="c703b-104">Utilisez la procédure suivante pour désactiver la prise d’appel de groupe pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c703b-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c703b-105">Lorsque vous désactivez la prise d’appel de groupe pour un utilisateur, le numéro de groupe de prise d’appel attribué à l’utilisateur n’est pas conservé.</span><span class="sxs-lookup"><span data-stu-id="c703b-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="c703b-106">Si vous souhaitez ensuite réactiver la prise d’appel de groupe pour cet utilisateur, vous devez à nouveau affecter le numéro de groupe de prise d’appel avec le paramètre/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="c703b-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="c703b-107">Pour désactiver la prise d’appel de groupe pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="c703b-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="c703b-108">Ouvrez une session sur l’ordinateur sur lequel vous avez installé l’outil SEFAUtil avec des droits d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="c703b-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="c703b-109">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c703b-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="c703b-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c703b-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c703b-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c703b-111">See Also</span></span>


[<span data-ttu-id="c703b-112">Affecter des numéros de prise d’appel de groupe aux utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c703b-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="c703b-113">Activer la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c703b-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

