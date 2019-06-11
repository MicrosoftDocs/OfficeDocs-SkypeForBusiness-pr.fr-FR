---
title: 'Lync Server 2013: New-CsWebServiceConfiguration pour la gestion du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a973ca1086a9d2ca1ce2d8f19bbb64ba8aae19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="f0bbc-102">Nouveauté-CsWebServiceConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0bbc-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0bbc-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f0bbc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f0bbc-104">Qui peut exécuter cette applet de commande: par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande New-CsWebServiceConfiguration: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f0bbc-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="f0bbc-105">Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f0bbc-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="f0bbc-106">Le cmdlet New-CsWebServiceConfiguration définit une nouvelle configuration pour les services Web de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f0bbc-106">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization.</span></span> <span data-ttu-id="f0bbc-107">L’étendue de la configuration des services Web ne peut être qu’au niveau du site ou du service.</span><span class="sxs-lookup"><span data-stu-id="f0bbc-107">The scope for the Web Services configuration can only be at the site or service level.</span></span> <span data-ttu-id="f0bbc-108">Il n’est pas possible de créer une configuration de services Web au niveau global.</span><span class="sxs-lookup"><span data-stu-id="f0bbc-108">It cannot create a new Web Services configuration at the global level.</span></span> <span data-ttu-id="f0bbc-109">L’attribut EnableGroupExansion est particulièrement intéressant pour le carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="f0bbc-109">Specifically of interest to the Address Book is the EnableGroupExansion attribute.</span></span> <span data-ttu-id="f0bbc-110">Si elle a la valeur true, les services Web peuvent répondre aux demandes de développement de groupe.</span><span class="sxs-lookup"><span data-stu-id="f0bbc-110">If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="f0bbc-111">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f0bbc-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="f0bbc-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f0bbc-112">See Also</span></span>


[<span data-ttu-id="f0bbc-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="f0bbc-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

