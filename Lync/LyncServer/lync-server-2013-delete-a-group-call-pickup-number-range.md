---
title: 'Lync Server 2013 : suppression d’une plage de numéros de prise d’appel de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 179bde8b8e23cc21fb95fa93e3c6cbeb7f381630
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="f5bf3-102">Supprimer une plage de numéros de prise d’appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5bf3-102">Delete a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5bf3-103">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="f5bf3-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="f5bf3-104">Utilisez la procédure suivante pour supprimer une plage de numéros de prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="f5bf3-104">Use the following procedure to delete a Group Call Pickup number range.</span></span>

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a><span data-ttu-id="f5bf3-105">Pour supprimer une plage de numéros de groupe de prise d’appel</span><span class="sxs-lookup"><span data-stu-id="f5bf3-105">To delete a call pickup group number range</span></span>

1.  <span data-ttu-id="f5bf3-106">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f5bf3-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f5bf3-107">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f5bf3-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f5bf3-108">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="f5bf3-108">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    <span data-ttu-id="f5bf3-109">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f5bf3-109">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5bf3-110">Pour plus d’informations sur d’autres options, voir <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span><span class="sxs-lookup"><span data-stu-id="f5bf3-110">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5bf3-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5bf3-111">See Also</span></span>


[<span data-ttu-id="f5bf3-112">Création ou modification d’une plage d’orbites de parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5bf3-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="f5bf3-113">Remove-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="f5bf3-113">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="f5bf3-114">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="f5bf3-114">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

