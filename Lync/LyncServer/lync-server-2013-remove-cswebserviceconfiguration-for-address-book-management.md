---
title: 'Lync Server 2013 : Remove-CsWebServiceConfiguration pour la gestion des carnets d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove-CsWebServiceConfiguration for Address Book management
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429713(v=OCS.15)
ms:contentKeyID: 48184848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62ad914027fc1d406ba66d2dead2b8eab7601ff7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536491"
---
# <a name="remove-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="8e556-102">Remove-CsWebServiceConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e556-102">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e556-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8e556-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8e556-p101">Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes qui suivent sont autorisés à exécuter localement l’applet de commande Remove-CsWebServiceConfiguration : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="8e556-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

<span data-ttu-id="8e556-p102">L’applet de commande Remove-CsWebServiceConfiguration permet à un administrateur de supprimer une configuration des services web créée précédemment. L’applet de commande ne peut pas supprimer la configuration globale des services web.</span><span class="sxs-lookup"><span data-stu-id="8e556-p102">The Remove-CsWebServiceConfiguration cmdlet allows an administrator to remove a previously created Web Services configuration. The cmdlet cannot remove the global Web Services configuration.</span></span>

<span data-ttu-id="8e556-108">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8e556-108">For example:</span></span>

    Remove-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="8e556-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e556-109">See Also</span></span>


[<span data-ttu-id="8e556-110">Remove-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="8e556-110">Remove-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

