---
title: 'Lync Server 2013 : Set-CsAddressBookConfiguration pour la gestion des carnets d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsAddressBookConfiguration for Address Book management
ms:assetid: 3a64ceb1-9f79-4f3b-bf33-eaf346dbd60d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429700(v=OCS.15)
ms:contentKeyID: 48183913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7897d1441746430310d392456adacc6756f469d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="9bc5a-102">Set-CsAddressBookConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bc5a-102">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bc5a-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9bc5a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9bc5a-p101">Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes suivants sont autorisés à exécuter localement l’applet de commande Set-CsAddressBookConfiguration : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="9bc5a-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsAddressBookConfiguration"}

<span data-ttu-id="9bc5a-106">Set-CsAddressBookConfiguration est similaire à l’applet de commande New-CsAddressBookConfiguration, à la seule différence qu’elle sert à modifier une configuration existante.</span><span class="sxs-lookup"><span data-stu-id="9bc5a-106">Set-CsAddressBookConfiguration is similar to the New-CsAddressBookConfiguration cmdlet, except it is used to modify an existing configuration.</span></span>

<span data-ttu-id="9bc5a-107">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9bc5a-107">For example:</span></span>

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

<div>

## <a name="see-also"></a><span data-ttu-id="9bc5a-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9bc5a-108">See Also</span></span>


[<span data-ttu-id="9bc5a-109">Set-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="9bc5a-109">Set-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

