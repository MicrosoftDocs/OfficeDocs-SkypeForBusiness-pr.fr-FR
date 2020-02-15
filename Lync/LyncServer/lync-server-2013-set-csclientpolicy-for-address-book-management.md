---
title: 'Lync Server 2013 : Set-CsClientPolicy pour la gestion des carnets d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsClientPolicy for Address Book management
ms:assetid: e7788bea-606f-481a-a3a4-1855ac028493
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429723(v=OCS.15)
ms:contentKeyID: 48185726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f726e42d5827c153cac08a11e43d4e4f9423da1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="68e41-102">Set-CsClientPolicy pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68e41-102">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68e41-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="68e41-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="68e41-p101">Personnes autorisées à exécuter cette cmdlet : Par défaut, les membres des groupes qui suivent sont autorisés à exécuter localement la cmdlet Set-CsClientPolicy : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette cmdlet a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="68e41-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsClientPolicy cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClientPolicy"}

<span data-ttu-id="68e41-106">Comme la cmdlet New-CsClientPolicy, la cmdlet Set-CsClientPolicy vous permet de modifier les paramètres du client déjà en place.</span><span class="sxs-lookup"><span data-stu-id="68e41-106">Similar to New-CsClientPolicy, the Set-CsClientPolicy cmdlet allows you to modify client settings that are already in place.</span></span>

<span data-ttu-id="68e41-107">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="68e41-107">For example:</span></span>

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00" -AddressBookAvailability "WebSearchAndFileDownload"

<div>

## <a name="see-also"></a><span data-ttu-id="68e41-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68e41-108">See Also</span></span>


[<span data-ttu-id="68e41-109">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="68e41-109">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

