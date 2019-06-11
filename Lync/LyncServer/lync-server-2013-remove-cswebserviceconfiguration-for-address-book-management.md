---
title: 'Lync Server 2013: Remove-CsWebServiceConfiguration pour la gestion du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove-CsWebServiceConfiguration for Address Book management
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429713(v=OCS.15)
ms:contentKeyID: 48184848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 206c47ebb272f6ab637f4f07e9bb54a7fd1d40e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="3d0d3-102">Remove-CsWebServiceConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d0d3-102">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d0d3-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3d0d3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3d0d3-104">Qui peut exécuter cette applet de commande: par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande Remove-CsWebServiceConfiguration localement: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3d0d3-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="3d0d3-105">Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d0d3-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

<span data-ttu-id="3d0d3-106">L’applet de CsWebServiceConfiguration de suppression-suppression permet à un administrateur de supprimer une configuration de services Web précédemment créée.</span><span class="sxs-lookup"><span data-stu-id="3d0d3-106">The Remove-CsWebServiceConfiguration cmdlet allows an administrator to remove a previously created Web Services configuration.</span></span> <span data-ttu-id="3d0d3-107">L’applet de cmdlet ne peut pas supprimer la configuration globale des services Web.</span><span class="sxs-lookup"><span data-stu-id="3d0d3-107">The cmdlet cannot remove the global Web Services configuration.</span></span>

<span data-ttu-id="3d0d3-108">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="3d0d3-108">For example:</span></span>

    Remove-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="3d0d3-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d0d3-109">See Also</span></span>


[<span data-ttu-id="3d0d3-110">Remove-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="3d0d3-110">Remove-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

