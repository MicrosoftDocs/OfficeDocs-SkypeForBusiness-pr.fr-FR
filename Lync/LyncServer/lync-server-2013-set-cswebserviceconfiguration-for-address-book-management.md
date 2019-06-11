---
title: 'Lync Server 2013: Set-CsWebServiceConfiguration pour la gestion du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set-CsWebServiceConfiguration for Address Book management
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429709(v=OCS.15)
ms:contentKeyID: 48184572
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cb1fa5d6474a792442510181a5c13b17e074c61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="46489-102">Set-CsWebServiceConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46489-102">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46489-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="46489-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="46489-104">Qui peut exécuter cette applet de commande: par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande Set-CsWebServiceConfiguration localement: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="46489-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="46489-105">Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="46489-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

<span data-ttu-id="46489-106">La cmdlet Set-CsWebServiceConfiguration permet à l’administrateur de redéfinir un attribut existant dans la configuration des services Web.</span><span class="sxs-lookup"><span data-stu-id="46489-106">The Set-CsWebServiceConfiguration cmdlet allows the administrator to redefine an existing attribute in the configuration of the Web Services.</span></span>

<span data-ttu-id="46489-107">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="46489-107">For example:</span></span>

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

<div>

## <a name="see-also"></a><span data-ttu-id="46489-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46489-108">See Also</span></span>


[<span data-ttu-id="46489-109">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="46489-109">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

