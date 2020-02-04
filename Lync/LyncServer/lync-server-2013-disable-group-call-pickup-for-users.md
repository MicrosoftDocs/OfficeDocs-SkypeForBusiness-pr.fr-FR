---
title: 'Lync Server 2013 : désactiver le prélèvement d’appels de groupe pour les utilisateurs'
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
ms.openlocfilehash: f7e47b5c3b12997bd05f3721555a5dfdfe692bbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="60df8-102">Désactiver le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60df8-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60df8-103">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="60df8-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="60df8-104">Utilisez la procédure suivante pour désactiver le prélèvement d’appels de groupe pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="60df8-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60df8-105">Si vous désactivez le prélèvement d’appel de groupe pour un utilisateur, le numéro de groupe de capture d’appel qui a été affecté à l’utilisateur n’est pas conservé.</span><span class="sxs-lookup"><span data-stu-id="60df8-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="60df8-106">Si vous voulez par la suite réactiver le prélèvement d’appels de groupe pour cet utilisateur, vous devez de nouveau affecter le numéro de groupe de capture d’appel avec le paramètre/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="60df8-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="60df8-107">Pour désactiver le prélèvement d’appels de groupe pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="60df8-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="60df8-108">Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="60df8-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="60df8-109">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="60df8-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="60df8-110">Exemple :</span><span class="sxs-lookup"><span data-stu-id="60df8-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60df8-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="60df8-111">See Also</span></span>


[<span data-ttu-id="60df8-112">Attribution de numéros de numérotation des appels de groupe aux utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60df8-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="60df8-113">Activer le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60df8-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

