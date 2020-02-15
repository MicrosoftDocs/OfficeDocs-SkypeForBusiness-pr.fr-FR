---
title: 'Lync Server 2013 : New-CsWebServiceConfiguration pour la gestion des carnets d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccc4eafd9fd7db6173b14c17b44218c122ad01b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="43f4a-102">New-CsWebServiceConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43f4a-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43f4a-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="43f4a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="43f4a-p101">Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes suivants sont autorisés à exécuter localement l’applet de commande New-CsWebServiceConfiguration : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="43f4a-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="43f4a-p102">L’applet de commande New-CsWebServiceConfiguration définit une nouvelle configuration pour les services web de votre organisation. L’étendue de la configuration des services web ne peut être qu’au niveau du site ou du service. Elle ne peut pas créer une nouvelle configuration des services web au niveau global. L’attribut EnableGroupExpansion est particulièrement intéressant pour le carnet d’adresses. S’il est défini sur True, les services web peuvent répondre aux demandes de développement de groupes.</span><span class="sxs-lookup"><span data-stu-id="43f4a-p102">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization. The scope for the Web Services configuration can only be at the site or service level. It cannot create a new Web Services configuration at the global level. Specifically of interest to the Address Book is the EnableGroupExansion attribute. If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="43f4a-111">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="43f4a-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="43f4a-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43f4a-112">See Also</span></span>


[<span data-ttu-id="43f4a-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="43f4a-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

